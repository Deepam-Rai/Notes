
## Package Management Tools

|                        | dpkg                     | apt-get                               | apt                                                                               |
| ---------------------- | ------------------------ | ------------------------------------- | --------------------------------------------------------------------------------- |
| What?                  | Package management tool. | Package management tool. Uses `dpkg`. | Package management tool. Wrapper around `apt-get` and `apt-cache`                 |
| OS:                    | Debian & Debian based.   | Debian & Debian based.                | Debian & Debian based.                                                            |
| Dependency resolution: | No.                      | Yes.                                  | Yes.                                                                              |
| Backward compatible:   | Yes.                     | Yes.                                  | No.                                                                               |
| User friendly:         | No.                      | Less user-friendly.                   | Yes.                                                                              |
| Efficiency:            | -                        | Comparatively less than `apt`.        | Comparatively more than `apt-get`. In sense that many manual steps are automated. |
| Stable CLI Interface:  | Yes.                     | Yes.                                  | No.                                                                               |
|                        |                          |                                       |                                                                                   |

```shell
# listing installed packages
apt list --installed

# locally cached package information
apt-cache search <package>
apt-cache show <package>

# installation
apt install <package> -y

# removal
apt autoremove  # remove all unused packages
apt remove <package>  # uninstall but keep config 
apt purge <package>  # uninstall & remove config too
```

## Package Repositories
> Repositories are locations that contains essential and popular software for Linux distributions.

- each Linux distribution has its own official repositories - standard repositories.
- these repositories are queried when we install, upgrade packages.

Repositories used by the OS can be checked by following: `/etc/apt/sources.list` file.  


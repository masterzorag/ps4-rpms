# ps4-rpms

Some fc28, fc29, fc30 rpms with added ps4 support.  
We share and apply the [same patchset](https://github.com/Ps3itaTeam/ps4linux-video-drivers), result of [eeply](https://twitter.com/eeply) and [Ps3ita_Team](https://twitter.com/Ps3ita_Team) cowork.

* setup this repository
```sh
cd /etc/yum.repos.d/

wget https://raw.githubusercontent.com/masterzorag/ps4-rpms/master/ps4-rpms.repo

dnf repolist
```
* replace libdrm, from this repo
```
dnf reinstall libdrm* --repo ps4
Last metadata expiration check: 0:02:59 ago on Thu May 16 23:32:48 2019.
Dependencies resolved.
==================================================================================================================
 Package                       Architecture            Version                         Repository            Size
==================================================================================================================
Reinstalling:
 libdrm                        i686                    2.4.98-1.fc30                   ps4                  156 k
 libdrm                        x86_64                  2.4.98-1.fc30                   ps4                  143 k
 libdrm-devel                  i686                    2.4.98-1.fc30                   ps4                  147 k
 libdrm-devel                  x86_64                  2.4.98-1.fc30                   ps4                  147 k

Transaction Summary
==================================================================================================================

Total download size: 593 k
Installed size: 2.0 M
Is this ok [y/N]:
```
* same for mesa packages  
`dnf reinstall mesa* --repo ps4`

* install AMDGPU Xorg driver  
`dnf reinstall xorg-x11-drv-amdgpu* --repo ps4`

* keep system update, preserving current ps4 set  
`dnf update -x kernel*,libdrm*,mesa*,xorg-x11-drv-a*`

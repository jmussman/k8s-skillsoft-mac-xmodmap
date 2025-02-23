[//]: # (README.md)
[//]: # (Copyright © 2024 Joel A Mussman. All rights reserved.)
[//]: #

![Banner Light](https://raw.githubusercontent.com/jmussman/cdn-fun/main/banners/banner-k8s-skillsoft-mac-xmodmap-light.png#gh-light-mode-only)
![Banner Light](https://raw.githubusercontent.com/jmussman/cdn-fun/main/banners/banner-k8s-skillsoft-mac-xmodmap-dark.png#gh-dark-mode-only)

# Renew Kubernetes Certificates

## Overview

This is a solution for a specific problem with the skillable Learn on Demand virual environment for
the Building Kubernetes Skills class.
The Microsoft Azure image does not correctly map the keyboard for Apple MacOS, so ctrl-C does not work.

## Utilization

1. Check control-C; if it is working you can skip all of this, if you just see the letter "c"
then control-C is not working;
*labadmin@Udesktop:~$* is the initial prompt:
```
labadmin@Udesktop:~$ c
```
1. Download the .Xmodmap file from this repository

1. Execute a root shell; *labadmin@Udesktop:~$* is the initial prompt:
```
labadmin@Udesktop:~$ sudo bash
[sudo] password for labadmin:
root@Udesktop:~# 
```
1. Copy the file to the Labadmin and root home directories
```
root@Udesktop:~# cp ~labadmin/Downloads/.Xmodmap ~labadmin
root@Udesktop:~# cp ~labadmin/Downloads/.Xmodmap ~root
```
1. Edit the ~root/.bashrc file and add the following line to the end:
```
xmodmap ~/.Xmodmap
```
1. Add the same line to the end of ~labadmin/.bashrc
1. Exit the root shell:
```
root@Udesktop:~# exit
labadmin@Udesktop:~$
```
1. Source the .bashrc file in the original shell to apply the keyboard map:
```
labadmin@Udesktop:~$ . ~/.bashrc
```
1. Test control-C to make sure it works:
```
labadmin@Udesktop:~$ ^C
labadmin@Udesktop:~$
```

## See Also

* The Kubernetes installation scripts for various platforms at https://github.com/jmussman/k8s-install-scripts

## License

The code is licensed under the MIT license. You may use and modify all or part of it as you choose, as long as attribution to the source is provided per the license. See the details in the [license file](./LICENSE.md) or at the [Open Source Initiative](https://opensource.org/licenses/MIT).

<hr>
Copyright © 2025 Joel A Mussman. All rights reserved.
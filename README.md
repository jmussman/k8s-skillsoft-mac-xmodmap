[//]: # (README.md)
[//]: # (Copyright © 2025 Joel A Mussman. All rights reserved.)
[//]: #

![Banner Light](https://raw.githubusercontent.com/jmussman/cdn-fun/main/banners/banner-k8s-skillsoft-mac-xmodmap-light.png#gh-light-mode-only)
![Banner Light](https://raw.githubusercontent.com/jmussman/cdn-fun/main/banners/banner-k8s-skillsoft-mac-xmodmap-dark.png#gh-dark-mode-only)

# K8s skillsoft Mac Xmodmap

## Overview

Tha Microsoft Azure image used by the *skillsoft* Building Kubernetes Skills class does not
correctly map the keyboard for the Apple MacOS.
This prevents control-C (^C) from functioning.
This issue does not affect Microsoft Windows.

The repository contains a keymap that solves the problem.
Follow the instructions to install the keymap on the *skillsoft* virtual computers.

## Utilization

1. Check control-C; if it is working you can skip all of this, if you just see the letter "c"
then control-C is not working;
*labadmin@Udesktop:~$* is the initial prompt:
```
labadmin@Udesktop:~$ c
```
1. Click on the Xmodmap.txt file in the files tree.

1. Click the download button and save the file in your *Downloads* folder.
1. Open a terminal window.
1. Copy the file to the home directory as .Xmodmap:
```
labadmin@Udesktop:~$ cp ~/Downloads/Xmodmap.txt .Xmodmap
```
1. Edit the *.bashrc* file in the home directory (~/.bashrc) and add
a line at the end of the file to invoke .Xmodmap:
```
xmodmap ~/.Xmodmap
```
1. Copy the file to the root home directories
```
labadmin@Udesktop:~$ sudo cp ~/Downloads/Xmodmap.txt ~root/.Xmodmap
```
1. Sudo and edit the ~root/.bashrc file and add the following line to the end:
```
xmodmap ~/.Xmodmap
```
1. Source the .bashrc file to apply the keyboard map in terminal window:
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
# Arch mkinitcpio 39-1 vs 38.1-1 findings

This repo contains numerous kernel logs from [my laptop](#System) running Arch
Linux. In each case, the logs were obtained by booting the system, logging in,
and running

```
journalctl -b 0 -k > path/to/log/file
```

Packages were downgraded using `pacman -U` and the local cache for specific
packages, and `pacman -Syyuu` for restoring to an archive version state
(pointing pacman's `mirrorlist` to the specific archive URL, as detailed on
[the Arch Linux Archive page](https://wiki.archlinux.org/title/Arch_Linux_Archive#How_to_restore_all_packages_to_a_specific_date)).

The journals are organised as follows:

* pkg-archive-2024-05-03 -- System restored to the package archive from
    2024-05-03
* pkg-archive-2024-05-04 -- System restored to the package archive from
    2024-05-04
  - The log files with only the date are from the entire system being restored
      to this date
  - The log files with long names of specific packages were based on 2024-05-03
      and then had only the listed packages updated.
  - The log files with a seemingly random string and then a package name were
      similarly based on 2024-05-03, except with a newer 2024-05-04 version
      package appended every time, with accumulated packages being abbreviated
      to their first letter as split by dots and underscores.
* 2024-05-09-14-52-mkinitcpio39 -- System updated completely to the latest
    packages using the Arch mirrors as of 2024-05-09T14:52 UTC 
* 2024-05-09-14-52-mkinitcpio38.1 -- System updated to the latest packages using
    the Arch mirrors as of 2024-05-09T14:52 UTC, _except_ with mkinitcpio fixed
    to version 38.1 using `IgnorePkg = mkinitcpio` in `/etc/pacman.conf`


## System

* ThinkPad X1 Extreme (1st gen)
* arch: x86_64
* cpu: Intel Core i7-8750H
* dGPU: NVIDIA GP107M \[GeForce GTX 1050 Ti Mobile\] (rev a1)


## LICENSE 

This work is licensed under
[CC BY 4.0 ![license button](https://licensebuttons.net/l/by-sa/4.0/80x15.png)](https://creativecommons.org/licenses/by/4.0/?ref=chooser-v1).

See the [LICENSE](LICENSE) file.


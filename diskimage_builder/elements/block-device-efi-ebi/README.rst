========================
Block Device EFI for EBI
========================

This provides a block-device configuration for the ``vm`` element to
get a single-partition disk suitable for EFI booting.

In addition to 10% / filesystem, there is an additional partition created
to host lvm (rest of disk space).

Note on x86 this provides the extra `BIOS boot partition
<https://en.wikipedia.org/wiki/BIOS_boot_partition>`__ and a EFI boot
partition for maximum compatability.


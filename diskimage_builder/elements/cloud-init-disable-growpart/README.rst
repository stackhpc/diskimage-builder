===========================
cloud-init-disable-growpart
===========================

The cloud-init growpart module will extend / filesystem by default to maximum
free disk space. This removes it from cloud.cfg, putting the onus for resizing
on the user post-boot.

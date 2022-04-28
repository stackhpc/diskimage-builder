==========
bootloader
==========

Installs ``grub[2]`` on boot partition on the system.

Arguments
=========

* ``DIB_GRUB_TIMEOUT`` sets the ``grub`` menu timeout.  It defaults to
  5 seconds.  Set this to 0 (no timeout) for fast boot times.

* ``DIB_BOOTLOADER_DEFAULT_CMDLINE`` sets parameters that are appended
  to the ``GRUB_CMDLINE_LINUX_DEFAULT`` values in ``grub.cfg``
  configuration. It defaults to ``nofb nomodeset gfxpayload=text``.

* ``DIB_BOOTLOADER_SERIAL_CONSOLE`` sets the serial device to be
  used as a console. It defaults to ``hvc0`` for PowerPC, 
  ``ttyAMA0,115200`` for ARM64, otherwise ``ttyS0,115200``.

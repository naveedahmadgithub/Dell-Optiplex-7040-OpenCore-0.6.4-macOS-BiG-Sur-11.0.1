# Dell-Optiplex-7040-OpenCore-0.6.4-macOS-BiG-Sur-11.0.1

Successfully Installed BiG Sur on Dell Optiplex 7040 

°Bios Setup

•F2 key interning in bios

•Default Factory reset

•Uncheck Enable Legacy Option ROMS

•Disable Serial Port

•SATA Operation AHCI

•Disable TPM

•Disable VT

•Graphics auto to intel HD

Apply Save setting and Exit.


°UEFI Variables
In order to run macOS successfully a number of EFI BIOS variables need to be modified. The included OpenCore bootloader contains an updated
modGRUBShell.efi, which includes a setup_var command to help do just that.

modGRUBShell.efi can be launched from OpenCore directory in the tools folder.

The following variables need to be updated:

Variable Offset	Default value	Desired value	Comment

°CFG Lock	0xAF	0x01 (Enabled)	0x00 (Disabled)	Disable CFG Lock to prevent MSR 0x02 errors on boot

DVMT Pre-allocation	0x350	0x01 (32M)	0x03 (96M)	Increase DVMT pre-allocated size to 96M for Native macOS Support

°Modify DVMT variable step
Start up and enter OpenCore boot menu, select modGRUBShell.efi Start modGRUBShell.efi and enter.


°just run setup_var 0x350 0x3 using this cmd line

fine, the graphics is ok to boot up (macOS BiG Sur 11.0.1)

°Note: the UEFI Variables will lose after set BOIS to factory default!

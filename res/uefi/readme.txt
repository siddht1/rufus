This directory contains a flat image of the FAT UEFI:NTFS partition added by
Rufus for NTFS UEFI boot support. See https://github.com/pbatard/uefi-ntfs.

This image, which you can mount as FAT filesystem or open in 7-zip, contains
the following data:
o The NTFS UEFI drivers from efifs (https://github.com/pbatard/efifs) which were
  compiled, with compression disabled, using Visual Studio 2015 Community Edition.
  These are the \EFI\Rufus\ntfs_[ia32|x64].efi files.
o The UEFI:NTFS binaries (https://github.com/pbatard/uefi-ntfs), which were also
  compiled using Visual Studio 2015 Community Edition.
  These are the \EFI\Boot\boot[ia32|x64].efi files.

The FAT partition was created on Debian GNU/Linux using the following commands
  dd if=/dev/zero of=uefi-ntfs.img bs=512 count=512
  mkfs.vfat -n UEFI_NTFS uefi-ntfs.img
and then mounting the uefi-ntfs.img image and copying the relevant files.

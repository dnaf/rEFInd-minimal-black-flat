# Minimalistic flat black rEFInd theme

[rEFInd](http://www.rodsbooks.com/refind/) is a simplistic boot manager for UEFI
based systems. This is a clean and minimal black theme for it.

## Difference from rEFInd-minimal-black

Basically, I just made all the logos flatter. Here's a comparison of the Arch icon from rEFInd-minimal-black (left) and rEFInd-minimal-black-flat (right)

![rEFInd-minimal-black](./archonblack_black.png)
![rEFInd-minimal-black-flat](./archonblack_flat.png)

## Usage

 1. Locate your refind EFI directory. This is commonly `/boot/EFI/refind`
    though it will depend on where you mount your ESP and where rEFInd is
    installed. `fdisk -l` and `mount` may help.

 2. Clone this repository into your refind configuration directory.

 3. To enable the theme add `include rEFInd-minimal-black-flat/theme.conf` at the end of
    `refind.conf`.

Here's an example menuentry configuration (from the screenshot)

```nginx
menuentry "Arch Linux" {
	icon /EFI/refind/rEFInd-minimal-black-flat/icons/os_arch.png
	loader vmlinuz-linux
	initrd initramfs-linux.img
	options "rw root=UUID=dfb2919d-ff78-48db-a8a7-23f7542c343a loglevel=3"
}

menuentry "Windows" {
	icon /EFI/refind/rEFInd-minimal-black-flat/icons/os_win.png
	loader /EFI/Microsoft/Boot/bootmgfw.efi
}

menuentry "OSX" {
	icon /EFI/refind/rEFInd-minimal-black-flat/icons/os_mac.png
	loader /EFI/Apple/Boot/bootmgfw.efi
}
```

Entries that are autodetected should also show the proper icons.

## Attribution

The OS icons are from [Lightness for burg][icons] by [SWOriginal][icon-author].

[icons]: http://sworiginal.deviantart.com/art/Lightness-for-burg-181461810
[icon-author]: http://sworiginal.deviantart.com/

[padster]: https://github.com/theRealPadster

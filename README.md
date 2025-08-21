## Minimalistic ROG rEFInd theme

[rEFInd](http://www.rodsbooks.com/refind/) is an easy to use boot manager for UEFI
based systems. This is a clean and minimal theme for it.

![ROG rEFInd Minimalistic](./showcase.png)

---

### Usage

1.  Locate your refind EFI directory. This is commonly `/boot/EFI/refind`
    though it will depend on where you mount your ESP and where rEFInd is
    installed. `fdisk -l` and `mount` may help.

2.  Create a folder called `themes` inside it, if it doesn't already exist

3.  Clone this repository into the `themes` directory.

4.  To enable the theme add `include themes/rEFInd-minimal/theme.conf` at the end of
    `refind.conf`.

Here's an example menuentry configuration (from the screenshot)

```nginx
menuentry "Arch Linux" {
	icon /EFI/refind/themes/rEFInd-minimal/icons/os_arch.png
	loader vmlinuz-linux
	initrd initramfs-linux.img
	options "rw root=UUID=dfb2919d-ff78-48db-a8a7-23f7542c343a loglevel=3"
}

menuentry "Windows" {
	icon /EFI/refind/themes/rEFInd-minimal/icons/os_win.png
	loader /EFI/Microsoft/Boot/bootmgfw.efi
}

menuentry "OSX" {
	icon /EFI/refind/themes/rEFInd-minimal/icons/os_mac.png
	loader /EFI/Apple/Boot/bootmgfw.efi
}
```

Entries that are autodetected should also show the proper icons.

---

### Background sizes

If you find the background looks blurry it may be due to the included wallpaper
being an incorrect resolution for your monitor. You can download the [original
high quality wallpaper][wallpaper], resize it as appropriate, and replace the
`background.png`.

You can of course also choose your own background!

### Icon Requests

The theme is made for my use case, if you like it and want to make add other OS icons then you can raise a feature request and I'll add it. As always pull requests are preferred.

PS: All the icons have 320x320px image size.

### Attribution

The background is [ROG Wallpaper Challenge - 37][wallpaper] from ROG Wallpaper challenge 2017.

[wallpaper]: https://rog.asus.com/wallpapers/yourcreation/

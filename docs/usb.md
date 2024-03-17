# Format usb flash drive from macos
example: https://apple.stackexchange.com/questions/171506/formatting-usb-disk-as-ext3-on-mac

install `brew, visit http://brew.sh/`
install e2fsprogs using `brew install e2fsprogs`
figure out the name of your partition or drive using `diskutil list` -- in my case, my partition had was on disk2 and had the identifier of disk2s1
If the drive is mounted, unmount it: diskutil unmountDisk disk2. Note that this is the drive in the listing above, not the partition.
`sudo $(brew --prefix e2fsprogs)/sbin/mkfs.ext3 /dev/disk2s1` but you may need to change the drive from disk2s1 to the partition or drive that you want to format. This command will ask you to verify the name of the partition, just to be sure :)
Note, if you're able to ssh/telnet into your router running dd-wrt or tomato, you can already directly run mkfs.ext3 directly in the router, and don't need to do anything on your mac at all

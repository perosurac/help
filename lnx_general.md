=============================================================
IMAGING
=============================================================

Imaging with dc3dd
$ sudo dc3dd if=<device_name> hof=<image_filename> hash=md5 log=<log_filename>

  Example : sudo dc3dd if=/dev/sdh hof=./SOMALIA_USBK01.dd hash=md5 log=./SOMALIA_USBK01.log

=============================================================
RSYNC
=============================================================

Sync only by types of file extension
$ rsync -av --include='*/' --include-from=<file-with-extensions> --exclude='*' --prune-empty-dirs <source> <destination>

  Explainations :
  - --include='*/' : to be sure all the sub-directories are scanned
  - --prune-empty-dirs : do not create the subfolders if there is no matching file
  - --include-from must be before --exclude

  Example of content of the file with the extensions to sync :
  *.jpg
  *.jpeg
  *.tif
  *.doc
  *.docx

Sync and convert latin1 to utf8 on the fly
$ rsync -avrq --iconv=latin1,utf8 <source> <destination>

  Rmk : r for recursive / q for quiet (only show errors)

=============================================================
DEVICE MOUNTING
=============================================================

Mount a device just like it has to !
$ udisksctl mount --block-device=<device>

=============================================================
SYSTEM INFORMATION
=============================================================

Get size in bytes
$ blockdev --getsize64 /dev/sda

Get size of a block
$ blockdev --getbsz /dev/sda

=============================================================
BASH SHORTCUTS
=============================================================

History
$ !! -->  Repeat previous command
$ !4 -->  Repeat the 4th command in history
$ !ps --> Repeat the previous command in history that starts with "ps"
$ !$ --> Is the last param from the last command ex: ls !$

Moving the Cursor
- Ctrl+A or Home --> Go to the beginning of the line
- Ctrl+E or End --> Go to the end of the line
- Alt+B --> Go left (back) one word
- Ctrl+B --> Go left (back) one character
- Alt+F --> Go right (forward) one word
- Ctrl+F --> Go right (forward) one character

Deleting Text
- Ctrl+D or Delete --> Delete the character under the cursor
- Alt+D --> Delete all characters after the cursor on the current line
- Ctrl+H or Backspace --> Delete the character before the cursor

Cutting and Pasting
- Ctrl+W --> Cut the word before the cursor, adding it to the clipboard
- Ctrl+K --> Cut the part of the line after the cursor, adding it to the clipboard
- Ctrl+U --> Cut the part of the line before the cursor, adding it to the clipboard
- Ctrl+Y --> Paste the last thing you cut from the clipboard. The y here stands for “yank”

=============================================================
NETWORK
=============================================================
Map a Windows shared folder
$ mount [-t smbfs] -o username=<username> //<ip server>/<sharename> <mount point>

=============================================================
CHARACTER ENCODING
=============================================================
Convert filenames from one encoding to another

In 2 steps :
$ convmv -f latin1 -t utf-8 *
$ convmv --notest -f latin1 -t utf-8 *

=============================================================
MIDNIGHT COMMANDER
=============================================================
Filename in clipboard

1. Choose file then Ctl+Shift+Enter
2. Select the filename in the bottom line with Shift+MouseLeftClickSelect
3. Copy the text with Ctl+Insert
4. For paste Shift+Insert

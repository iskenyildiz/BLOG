# Notes for myself for future reference.


### Changes owner of a file.

`
chown user filename
`


### See files and line numbers with less(read only)

`
less -N <filename>
`  

use '/' to find a highlight of matching words.

### To find mounted filesystems

`
findmnt -l
`

### To list all active sockets.

`
ss -to
`

### To see statistics of a server. (ports etc.)

`
nmap google.com
`

### To change the filename when downloading with wget.

`
wget http://file.zip > filename
`

### To increase password timeout in ubuntu

open `sudo visudo`

add `Defaults        env_reset,timestamp_timeout=20`

# swd
It allows you to quickly deploy simple static HTML pages to your server. For now this script works only with Apache2.

## Installation

**Server preparation:**
1. Set the same account name either on server and pc.
2. Create group called `swd` and add your user to this group.
3. Set `swd` as `sites-enabled`'s group-owner.
4. Allow group to write files in `sites-enabled`.
5. Add
```
%swd ALL = (ALL) NOPASSWD: /etc/init.d/apache2 reload
%swd ALL = (ALL) NOPASSWD: /bin/systemctl reload apache2.service
```
into `/etc/sudoers` file (tested on Ubuntu). Following lines allow users from group `swd` to reload apache2 without entering password.

**Proper installation:**
1. Clone this repository.
2. Change value of `server_websites_dir`. This variable contains directory path where websites are stored on your server.
3. Done!

## Usage

Swd needs two parameters:
1. path to website directory
2. server name (e.g from `/etc/hosts`)

**EXAMPLE USAGE**

`swd ~/html/homepage mars`

## License

```
            DO WHAT THE FUCK YOU WANT TO PUBLIC LICENSE
                    Version 2, December 2004

 Copyright (C) 2004 Sam Hocevar <sam@hocevar.net>

 Everyone is permitted to copy and distribute verbatim or modified
 copies of this license document, and changing it is allowed as long
 as the name is changed.

            DO WHAT THE FUCK YOU WANT TO PUBLIC LICENSE
   TERMS AND CONDITIONS FOR COPYING, DISTRIBUTION AND MODIFICATION

  0. You just DO WHAT THE FUCK YOU WANT TO.
```

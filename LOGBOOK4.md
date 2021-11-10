# Work developed in week 4

## **Lab Tasks**

### Task 1

Important variables: PATH, LIBRARY, LOAD

- Printing all out the environment variables

```bash
[11/10/21]seed@VM:~/.../Labsetup$ env
SHELL=/bin/bash
SESSION_MANAGER=local/VM:@/tmp/.ICE-unix/2030,unix/VM:/tmp/.ICE-unix/2030
QT_ACCESSIBILITY=1
COLORTERM=truecolor
XDG_CONFIG_DIRS=/etc/xdg/xdg-ubuntu:/etc/xdg
XDG_MENU_PREFIX=gnome-
GNOME_DESKTOP_SESSION_ID=this-is-deprecated
GNOME_SHELL_SESSION_MODE=ubuntu
SSH_AUTH_SOCK=/run/user/1000/keyring/ssh
XMODIFIERS=@im=ibus
DESKTOP_SESSION=ubuntu
SSH_AGENT_PID=1995
GTK_MODULES=gail:atk-bridge
DBUS_STARTER_BUS_TYPE=session
PWD=/home/seed/Desktop/seed-labs/category-software/Environment_Variable_and_SetUID/Labsetup
LOGNAME=seed
XDG_SESSION_DESKTOP=ubuntu
XDG_SESSION_TYPE=x11
GPG_AGENT_INFO=/run/user/1000/gnupg/S.gpg-agent:0:1
XAUTHORITY=/run/user/1000/gdm/Xauthority
WINDOWPATH=2
HOME=/home/seed
USERNAME=seed
IM_CONFIG_PHASE=1
LANG=en_US.UTF-8
LS_COLORS=rs=0:di=01;34:ln=01;36:mh=00:pi=40;33:so=01;35:do=01;35:bd=40;33;01:cd=40;33;01:or=40;31;01:mi=00:su=37;41:sg=30;43:ca=30;41:tw=30;42:ow=34;42:st=37;44:ex=01;32:*.tar=01;31:*.tgz=01;31:*.arc=01;31:*.arj=01;31:*.taz=01;31:*.lha=01;31:*.lz4=01;31:*.lzh=01;31:*.lzma=01;31:*.tlz=01;31:*.txz=01;31:*.tzo=01;31:*.t7z=01;31:*.zip=01;31:*.z=01;31:*.dz=01;31:*.gz=01;31:*.lrz=01;31:*.lz=01;31:*.lzo=01;31:*.xz=01;31:*.zst=01;31:*.tzst=01;31:*.bz2=01;31:*.bz=01;31:*.tbz=01;31:*.tbz2=01;31:*.tz=01;31:*.deb=01;31:*.rpm=01;31:*.jar=01;31:*.war=01;31:*.ear=01;31:*.sar=01;31:*.rar=01;31:*.alz=01;31:*.ace=01;31:*.zoo=01;31:*.cpio=01;31:*.7z=01;31:*.rz=01;31:*.cab=01;31:*.wim=01;31:*.swm=01;31:*.dwm=01;31:*.esd=01;31:*.jpg=01;35:*.jpeg=01;35:*.mjpg=01;35:*.mjpeg=01;35:*.gif=01;35:*.bmp=01;35:*.pbm=01;35:*.pgm=01;35:*.ppm=01;35:*.tga=01;35:*.xbm=01;35:*.xpm=01;35:*.tif=01;35:*.tiff=01;35:*.png=01;35:*.svg=01;35:*.svgz=01;35:*.mng=01;35:*.pcx=01;35:*.mov=01;35:*.mpg=01;35:*.mpeg=01;35:*.m2v=01;35:*.mkv=01;35:*.webm=01;35:*.ogm=01;35:*.mp4=01;35:*.m4v=01;35:*.mp4v=01;35:*.vob=01;35:*.qt=01;35:*.nuv=01;35:*.wmv=01;35:*.asf=01;35:*.rm=01;35:*.rmvb=01;35:*.flc=01;35:*.avi=01;35:*.fli=01;35:*.flv=01;35:*.gl=01;35:*.dl=01;35:*.xcf=01;35:*.xwd=01;35:*.yuv=01;35:*.cgm=01;35:*.emf=01;35:*.ogv=01;35:*.ogx=01;35:*.aac=00;36:*.au=00;36:*.flac=00;36:*.m4a=00;36:*.mid=00;36:*.midi=00;36:*.mka=00;36:*.mp3=00;36:*.mpc=00;36:*.ogg=00;36:*.ra=00;36:*.wav=00;36:*.oga=00;36:*.opus=00;36:*.spx=00;36:*.xspf=00;36:
XDG_CURRENT_DESKTOP=ubuntu:GNOME
VTE_VERSION=6003
GNOME_TERMINAL_SCREEN=/org/gnome/Terminal/screen/1e22effc_867f_42a6_831b_da438f9377ea
INVOCATION_ID=6b505765caf749ffb10cfdb4c83edc34
MANAGERPID=1787
LESSCLOSE=/usr/bin/lesspipe %s %s
XDG_SESSION_CLASS=user
TERM=xterm-256color
LESSOPEN=| /usr/bin/lesspipe %s
USER=seed
GNOME_TERMINAL_SERVICE=:1.122
DISPLAY=:0
SHLVL=1
QT_IM_MODULE=ibus
DBUS_STARTER_ADDRESS=unix:path=/run/user/1000/bus,guid=44908fdb234b0bcd48b13442618b875e
XDG_RUNTIME_DIR=/run/user/1000
JOURNAL_STREAM=9:36883
XDG_DATA_DIRS=/usr/share/ubuntu:/usr/local/share/:/usr/share/:/var/lib/snapd/desktop
**PATH=/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/games:/usr/local/games:/snap/bin:.**
GDMSESSION=ubuntu
DBUS_SESSION_BUS_ADDRESS=unix:path=/run/user/1000/bus,guid=44908fdb234b0bcd48b13442618b875e
_=/usr/bin/env
```

- Set and unset an environment variable:

```bash
[11/10/21]seed@VM:~/.../Labsetup$ export greeting=hello
[11/10/21]seed@VM:~/.../Labsetup$ printenv greeting
hello
[11/10/21]seed@VM:~/.../Labsetup$ unset greeting
[11/10/21]seed@VM:~/.../Labsetup$ printenv greeting
[11/10/21]seed@VM:~/.../Labsetup$
```

### Task 2

After doing Step1 and Step2, two different files where created. Both of them contain the same systems environment variables. We can conclude that the child process inherited the variables.

Output after `diff` :

```bash
[11/10/21]seed@VM:~/.../Labsetup$ diff -s task2s1.txt task2s2.txt
Files task2s1.txt and task2s2.txt are identical
```

### Task 3

In Step1, the file created was empty. In Step2 the file contained the environment variables. This happened because we changed the `execve()` invocation, passing in the 3rd parameter the environment variables of the main program, through the `environ` variable. More details in `man environ`.

### Task 4

From `man system` :

> The system() library function uses fork(2) to create a child process that executes the shell
command specified in command using execl(3) as follows:  `execl("/bin/sh", "sh", "-c", command, (char *) NULL);`
> 

After compiling and running the code, the output showed the environment variables.

### Task 5

After setting some environment variables in the user’s shell process, the program was executed with the root ownership and Set-UID. In the variables outputed by the program, the new ones set in the user shell where present. This is quite dangerous since a normal user can set new/modify existing environment variables, and by changing them, malicious users can control the behaviour of the Set-UID program.

### Task 6

After changing the PATH variable, the */home/seed* path was added to the begining of the varaible. Therefore a malicious user can run a programn called *ls,* in */home/seed* path, since  the `system` call has a relative path instead of the */bin/ls.*

## **CTF write-up/resolution**

### Challenge 1

Enter [http://ctf-fsi.fe.up.pt:5001/](http://ctf-fsi.fe.up.pt:5001/), go to **Shop** and choose the **WordPress Hosting** item. Then select **Aditional information** and we can see the plugins' versions. After searching for authentication CVEs related to both plugins, an CVE for **WordPress Plugin WooCommerce Booster Plugin 5.4.3** was found. The flag for this challenge is `flag{CVE-2021-34646}`.

### Challenge 2

The code for the exploit related to the CVE can be found in [exploitdb](https://www.exploit-db.com/exploits/50299). After running the python script with `python3 ./exploit_CVE-2021-34646.py http://ctf-fsi.fe.up.pt:5001/ 1`, several links were generated, one of them allowed to bypass authentication and login as the *admin*. Since we are logged in, we can now access [http://ctf-fsi.fe.up.pt:5001/wp-admin/edit.php](http://ctf-fsi.fe.up.pt:5001/wp-admin/edit.php), and then we click on the private post, which contains the flag.

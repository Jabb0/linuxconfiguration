# The ultimative guide of how not to be a pleb



# OS:

## Linux - Pop!_OS by System76. This is a well known hardware vendor. The system is a convenient custom Ubuntu. 
Version: 19.10 or 18.04 LTS
- Easy to install. Recommended with disk encryption and as clean install.
- Pick the version with integrated NVIDIA drivers if you have a NVIDIA card
Link: https://system76.com/pop
- For laptops POP OS allows switching between the integrated and the NVIDIA graphic to save power.

`sudo apt update && sudo apt upgrade`

# Desktop:
The OS ships with GNOME. I recommend extending it with a few plugins.

## Dash to Dock
Like the MacOS task dock?
https://extensions.gnome.org/extension/307/dash-to-dock/
https://micheleg.github.io/dash-to-dock/

## system-monitor
Enables displaying of the current resource stats in realtime
Requires dependencies:
`sudo apt install gir1.2-gtop-2.0 gir1.2-nm-1.0  gir1.2-clutter-1.0`

https://extensions.gnome.org/extension/120/system-monitor/
https://github.com/paradoxxxzero/gnome-shell-system-monitor-applet

## For Laptops there are also CPU frequency management tools

## gnome tweaks
the gnome tweak tool allows further customisation of the GUI. Also used for extension management.
`sudo apt install gnome-tweak-tool`

## "GNOME is for n00bs"

Well in that case use the tiling window manager i3 instead. It is really easy to install and can be selected in the user login mask. I will not cover that here. There are good tutorials out there how to set up i3, i3-lock and i3-status-bar.


# Shell
## zsh - another shell variant. 
Available via apt.
`sudo apt install zsh`
https://github.com/ohmyzsh/ohmyzsh/wiki/Installing-ZSH
After install use the option that sets defaults to the conf file.

## oh-my-zsh
Open source plugin manager allowing for nice customisation of zsh with productivity increase.
https://github.com/ohmyzsh/ohmyzsh
I recommend using the robbyrussel theme and the git extension as a minimum. And to enable waiting dots for autocompletion. The rest is pretty good explained.

## Alias config
I also recommend adding usefull alias to the .zshrc script (Note it is not .bashrc anymore).
For example `alias ll='ls -l'`

I usually have a alias for cd into project repositories and these:

```
# enable color support of ls and also add handy aliases
if [ -x /usr/bin/dircolors ]; then
    test -r ~/.dircolors && eval "$(dircolors -b ~/.dircolors)" || eval "$(dircolors -b)"
    alias ls='ls --color=auto'
    #alias dir='dir --color=auto'
    #alias vdir='vdir --color=auto'

    alias grep='grep --color=auto'
    alias fgrep='fgrep --color=auto'
    alias egrep='egrep --color=auto'
fi

# colored GCC warnings and errors
#export GCC_COLORS='error=01;31:warning=01;35:note=01;36:caret=01;32:locus=01:quote=01'

# some more ls aliases
alias ll='ls -alF'
alias la='ls -A'
alias l='ls -CF'

# Add an "alert" alias for long running commands.  Use like so:
#   sleep 10; alert
alias alert='notify-send --urgency=low -i "$([ $? = 0 ] && echo terminal || echo error)" "$(history|tail -n1|sed -e '\''s/^\s*[0-9]\+\s*//;s/[;&|]\s*alert$//'\'')"'
```



# Terminal window

As the default terminal is limited in features I really like a tiling terminal emulator.

## Tilix

Open source terminal emulator allowing to create new terminals in the same window and use them fullscreen.

https://gnunn1.github.io/tilix-web/

`sudo apt install tilix`

I like: 

- Appearance->Window Style->Borderless
- Appearance->Theme variant->Dark
- Profiles->Default->Color->Color scheme->Linux

and of course use "UTF-8 Unicode" as encoding.




# IDEs
## Visual Studio Code or Atom
Both can be found in the Pop! Store.

## JetBrains tools

The tools made by JetBrain are really developer friendly. I could not work without them. They are perfectly integrated into linux and now offer a easy to use installer in the form of the JetBrains Toolbox.

https://www.jetbrains.com/de-de/toolbox-app/

## JetBrains PyCharm

The only true Python IDE. Free community edition. Really nice free student programm.

Available via snaps or a toolbox app. Also possible with direct install but a bit tedious.

`snap install [pycharm-professional|pycharm-community] --classic`

-> `snap install pycharm-professional--classic`

or https://www.jetbrains.com/de-de/toolbox-app/

## JetBrains WebStorm

The only true Javascript and HTML IDE for web developers.

Also available via toolbox app or snap / direct install.

## Android Studio

In fact just another JetBrains product but free and from Google.

Also available via toolbox app or snap / direct install.

Android Studio requires some additional SDK. This is handled upon first start.



# Markdown editor
## Typora
A very nice editor for markdown content
https://www.typora.io/#linux



# Multi media
Install Spotify via the Pop! Store



# Browser

Pop OS ships out of the box with Firefox. I personally found it to be slow. So I am using chromium.

In case you want to watch Netflix and other DRM protected media you might want to use chrome. The install is again super easy via .deb package directly by google.

## Plugins

I really recommend two must have plugins for chrome, chromium and firefox:

- uMatrix: A really powerful resource and script blocker. You do not want everybody to run javascript on your machine.
- uBlock origin: Same author as uMatrix. A really resource friendly Ad Blocker. Because screw ads.



# SSH Keys

Having a proper SSH key is crucial for working with remote servers. Create one with a nice eliptic curve security and password protect them.

https://www.ssh.com/ssh/keygen

`ssh-keygen -t ecdsa -b 521`

`
Generating public/private ecdsa key pair.
Enter file in which to save the key (/home/jabb0/.ssh/id_ecdsa):`

You could also use rsa and end up with the known id_rsa ssh key.

Remember you can copy your public key to machines conveniently with `ssh-copy-id`

You can now copy the public key to gitlab, github and so on.



# Keepass2

Known from Windows as "Keepass2" we also want a key management tool. For linux it is called "KeepassXC". Again open source and compatible with the Keepass files.

It can be installed via the Pop store.

**Sync** KeePass has plugins that allow to sync your file between devices. You could use a SSH server or a onecloud but also the public cloud to store your keyfile. I am not using this feature as I like to have some separation of concerns here too. 



# Keyboard shortcuts

The real pros never touch their mouse again. Learn the shortcuts for moving windows and using workspaces. You can set them in the settings app. This is Linux, feel free to set whatever you like.

# Docker

Installing docker is documented on the docker wiki 

https://docs.docker.com/install/linux/docker-ce/ubuntu/

There exists also a easy to use script for the task:

https://get.docker.com/

Unfortunally this script requires some tweaks if your current OS is not already supported. E.g. 19.10 might not be stable right now. In that case you need to follow the instructions in the wiki and use "disco" which stands for 19.04. instead. This is at the add-apt-repository section. Otherwise use the test channel instead.

But yeah. If you really wanted a stable and no bleeding edge system you should have used the Ubuntu 18.04 LTS version.

Per default a user is not allowed to execute docker commands. As they technically give him root privileges. If you still want to do so (instead of using sudo docker every time). Add your user to the docker usergroup:

`sudo usermod -aG docker your-user`

# Install azure and aws tooling

The azure (az command) and aws (aws command) CLI tooling installation is described here:

https://docs.microsoft.com/en-us/cli/azure/install-azure-cli-apt?view=azure-cli-latest

https://linuxhint.com/install_aws_cli_ubuntu/

https://docs.aws.amazon.com/cli/latest/userguide/install-cliv1.html



# Backup tooling

For backups I can really recommend `borg` it is a deduplicating backup software, open source and supports encryption.

https://borgbackup.readthedocs.io/en/stable/

# Email client

## Thunderbird

The got to client here is thunderbird in my opinion. Or you use the CLI if you are brave.

In case you need to connect it to a company Exchange server use the next tool.

## DAVMail

Is a local SMTP proxy for accessing a company Exchange server and allowing to use thunderbird instead of outlook.

Also supports for calendar integration.

http://davmail.sourceforge.net/

# Messaging

## Rambox

Rambox is a tool used to have all your messenger services in a common place. Slack, telegram, whatsapp etc. 

It can be installed via a snap.

## Pidgin

Can be integrated with XMPP and therefore CISCO Jabber. Simple chat solution.

## Teams

Yes. Microsoft teams is now available for Linux.

https://teams.microsoft.com/downloads



# Also using the system for gaming

Gaming on Linux becomes more convenient now.

## Steam 

can be installed from the Pop Shop

## Lutris

Allows to control steam, steam for windows, native linux or wine games. 

Can be installed from the Pop Shop.

## Teamspeak

Can be downloaded from the teamspeak webpage. I recommend unpacking into /opt/teamspeak3 and creating a desktop shortcut in `~/.local/share/applications/teamspeak.desktop` with

```
[Desktop Entry]
Type=Application
Encoding=UTF-8
Name=Teamspeak
Comment=Teamspeak 3 Client
Exec=/opt/teamspeak3/ts3client_runscript.sh
Terminal=false
Categories=Teamspeak;Gaming;Application
Icon=/opt/teamspeak3/icon.jpg
StartupWMClass=ts3client_linux_amd64
```

## Prismatik

In case you got yourself a awesome LED ambilight for your monitor you can control it with the PRISMATIK tool. I recommend using the fork of psieg https://github.com/psieg/Lightpack/#build-instructions-for-linux. Compilation works like a charm. Just the UDEV rule for accessing the ttyUSB0 needs to be set in `sudo nano /etc/udev/rules.d/01-ttyusb0.rules`

`SUBSYSTEMS=="usb-serial", TAG+="uaccess", GROUP="dailout", MODE="0666"`





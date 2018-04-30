# kali-anonstealth, ParrotSec's anonsurf and stealth package, ported to work with Kali-Linux & Devuan.

++ How to use this package repositorie ++

This repo contains the sources of both the anonsurf and pandora packages from "ParrotSec" combined into one.
Modifications have been made to use the DNS servers of Private Internet Access (instead of FrozenDNS),
and fixes for users who don't use the resolvconf application.
= Removed gui and iceweasel in ram ==

This repo can & does, compile & build, a ".deb" package, to correctly install it on a Debian-Based system.

+++ NOTE: This may work with any debian/devuan/ubuntu system, but this has only been tested to work on a:
 "Kali-rolling amd64" system & a "Devuan ascii amd64" system.
 
++ It is advised not to download the ".zip" file, but instead to install "git", & use: "git clone". ++

user@mypc:~$ git clone https://git.devuan.org/stanz/my_anon.git

It may also be best - to install the "tor" package, before continuing.

========================================================================

The easiest way to get this installed/built & working is to run the installer.

=== Installation ===

Open your terminal of choice and enter the newly created/cloned "my_anon" folder.

user@mypc:~$ cd my_anon

user@mypc:~/my_anon$

user@mypc:~/my_anon$ sudo bash ./installer.sh ("This script must be ran as root")

The installer will take care of installing i2p, & all dependencies. Watch for any errors concerning packages
not found or installable. Issues can be posted on GitLab, for quickest response/fix.
Once the installer is complete, with no errors, you will be able to use "anonsurf, i2p, and pandora" modules.

+++ Anonsurf will anonymize the entire system under "tor" using "IPTables".****might need to be a pre-install?****
It will also allow you to start and stop i2p as well.

+++ NOTE: DO NOT run this as "service anonsurf $COMMAND", instead use "anonsurf $COMMAND".
example : "user@mypc:sudo anonsurf start".

Anonsurf Usage:

 ~$ anonsurf {start|stop|restart|change|status}

 start - Start system-wide anonymous tunneling under TOR proxy through iptables
          
 stop - Reset original iptables settings and return to clear navigation
 
 restart - Combines "stop" and "start" options
 
 change - Changes identity restarting TOR
 
 status - Check if AnonSurf is working properly
 

++ Be prepared for 1st run failure. Confirm success/failure, by checking your ip addy at: http://start.parrotsec.org/


If ip is your real ip, use: ~$ anonsurf restart


++ Not starting the "tor daemon" seems to be first fail, but done with restart.


i2p Usage:

 ~$ anonsurf {starti2p|stopi2p}

----[ I2P related features ]----

 starti2p - Start i2p services
 
 stopi2p - Stop i2p services

Pandora Usage:

In terminal: "user@mypc:~$ sudo bash pandora bomb"

Pandora automatically overwrites the RAM when the system is shutting down.

+++ NOTE: This will clear the entire system cache, including active SSH tunnels or sessions.
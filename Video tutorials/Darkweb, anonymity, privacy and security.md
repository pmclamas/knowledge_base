**Privacy -** a state in which one is not observed by others (id = known | activity = unknown)
**Anonymity -** a state where the acting person's name is unknown (id = unknown | activity = known)

##### Tails
- OS designed to be private and anonymous
- leave no traces
- runs entirely from portable storage

##### TOR network
you can configure your computer to route all traffic through the TOR Network.
- Problems:
	- internet speed will dramatically drop
	- difficult to prevent leaks
	- web browser can also leak information
	- data leaves the exit node un-encrypted
- Solution:
	- use TOR browser -> simplest, but not best
	- Tails -> great
	- Qubes OS with Whonix -> Best

##### TOR Browser
- modified version of Firefox ESR
- uses the TOR network by default
- fully patched
- disables insecure features/plugins
- forces all connections over https (using https-everywhere plugin)
- disables scripts (using noscript plugin)

##### VPN
**Benefits**
- extra layer of encryption
- more privacy and anonymity
- bypass censorship
- protection from hackers (prevents MITM attacks)
- use reputable VPN
- free VPN providers keep logs of your traffic (make sure you use a VPN that doesn't keep logs)
- use https-everywhere

**Tails as a VM loses lots of its benefits:**
- not fully live
- leaves traces
- not portable
- not private
- not as secure

### Best option is Tails on usb flash drive

**Starting Tails**
1. connect Tails usb
2. start/restart computer
3. enter the boot menu
4. boot from usb/external storage

**Tails - Persistence**
Tails is live and amnesic. Never uses computer storage. Only relies on RAM.
	**Benefits -** improved security, privacy and anonymity
	**Disadvantages -** can't store anything.

- Enable Persistence on Tails
	- persistence allows us to store files on Tails
	- computer storage is still left untouched
	- uses space left on the usb flash drive
	- the persistent volume is encrypted with a passphrase
	- at boot you'll have the choice to unlock the persistent storage

- Benefits of Tails with Persistence enabled:
	- store files, passwords, keys, etc
	- modify settings
	- install programs/plugins
- Disadvantages:
	- more unique = easier to detect
	- incorrect settings or vulnerable software can compromise your anonymity. 


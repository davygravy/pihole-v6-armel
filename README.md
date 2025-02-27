# Pi-hole v6 on Debian armel/Kirkwood ARMv5TE

While official **Pi-hole v6 support** for this SoC was dropped by the Pi-hole project due to some build difficulties, we aim to maintain it for as long as we can.  Disclaimer: Use at your own risk, no warranty is expressed or implied.

#### Disclaimer
N.B. This site and contents are unofficial, and _not maintained_ by the Pi-Hole team at https://pi-hole.net/ . They do not support this older (1998!) architecture effort, so don't expect or demand help there.  But you might get lucky.

## Description
Pi-hole v5 support was added in 2021 or thereabouts. The move to v6 precipitated some changes in the build system, and this ARMv5TE architecture was dropped.  As of Feb 26, 2025 there are three components now instead of five, things are simpler:

1. core 
    * scripts in `/opt/pihole/`
    * `pihole` script in `/usr/local/bin/`
    * configuration content in `/etc/pihole/` 
    * local git copy repo of v6 core in `/etc/.pihole/.git`
2. web
    * html/lua/scripts/images in`/var/www/html/admin`
    * local git copy repo of v6 web in `/var/www/html/admin/.git/`
    * perhaps an obsolete/orphan/v5 copy of lighttpd's landing page in `/var/www/html/index.lighttpd.html`
3. pihole-FTL (must be v6)
    * binary residing at `/usr/bin/pihole-FTL`

 
## Getting Started
As of Feb 26,2025, the standard install scripts will fail, due to the ARMv5TE architecture no longer being recognized.  With current code, there is no way to bypass the "architecture check", but we can bypass another check.


### Dependencies
* a working, updated Stable/Bookworm or Testing/Trixie Debian install on a Kirkwood/armel box (PogoPlug, Goflex, etc.).
* a rootfs/tarball for Trixie is available here - use at your own risk 
* normal dependencies called for by pihole/Pi-hole (note that in v6, php and lighttpd are no longer required)
* 

### OS Check Flag
* the install script makes use of quite a few checks, among them, **OS** and **Architecture**.
  * we can't get around the **Architecture** check
  * As of Feb 26, 2025, the **OS** check can be bypasses using the ENV flag : `PIHOLE_SKIP_OS_CHECK=true`
  * prepend this flag to a sequence commands on a line and it will skip that check for those commands
    


### Installing
*  `PIHOLE_SKIP_OS_CHECK=true`
*  

### Upgrading from v5
*
*

### Upgrading v6
*
*

### Assets
* rootfs for Debian Armel - Testing/Trixie (02/26/2025)
* 


### Adjustment/tweaks for memory usage
  * if your device has at least 256MB, that should be fine, depending on the number queries/second, client load and how long you keep your query records
  * on a Pogoplug V3 (OXNAS) or a Pogoplug v4/Mobile, you'll probably want to limit the size of the database by keeping records only for a week, or less
  * more coming...

### Version History - not yet...
* 0.2
    * Various bug fixes and optimizations
    * See [commit change]() or See [release history]()


## License
None yet...

## Acknowledgments
Inspiration, code snippets, etc.
* [Pi-hole](https://pi-hole.net/)
* [good, basic README-template.md](https://gist.githubusercontent.com/DomPizzie/7a5ff55ffa9081f2de27c315f5018afc/raw/d59043abbb123089ad6602aba571121b71d91d7f/README-Template.md)

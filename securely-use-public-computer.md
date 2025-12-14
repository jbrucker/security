## Can I Securely Use a Public Computer?

Logging into an account or entering confidential information on a public computer is **unsafe**.
A few of the ways your info can be stolen are:

- keystroke logger physically connected between keyboard and computer.
  - this actually happens!  If you trace the cable from keyboard to computer you will (probably) see a device inserted along the cable or between the cable connector and the port on the computer.
- some form of logger running on the OS.
  - may be a keystroke logger or similar malware running in a web browser
  - Windows 11 Recall feature, which constantly captures screen records
  - network monitor or tap.  May even perform a man-in-the-middle attack, since there could be a malicious root CA cert pre-installed on the computer.
- invisible screen sharing.  A privelaged app sharing your screen w/o any visible indication.

What if you really need to do something from a computer, but don't have your own computer?

Your first choice should be to try to do it using a web browser on your smartphone.

But if you really need to use an untrusted computer, a good solution is to boot from a USB drive containing an in-memory, ephemeral OS.

## Portable, Bootable Operating Systems

- [Tails][tails]: in-memory, security-hardened Linux designed for this use.
  - includes both Tor and the regular Firefox + UBlock Origin
  - can use USB drive for encrypted persistent storage
  - Tor can be slow and may be blocked by some bank/financial sites. Follow boot instructions to enable non-Tor mode.
  - Download and Install on a USB drive using [Linux](https://tails.net/install/linux/index.en.html) or [Windows](https://tails.net/install/windows/index.en.html) 
- [Qubes OS][qubes]
  - Xen-based, disposable VMs.
  - more resource intensive, so may be slow when booted from USB
- "Live Boot" from a USB drive containing the [Ubuntu installer][ubuntu], [Knoppix][knoppix], or other OS.
  - Install the Ubuntu installer (ISO image) onto a USB drive. During boot you can select "Live" mode to run Ubuntu w/o touching the PC's hard drive.
  - Install image includes Firefox and few network utilities.

  [tails]: https://tails.net/install/
  [ubuntu]: https://ubuntu.com/download

For your use case of logging into a financial account from an untrusted PC at a customer service office, here is a clean recommendation:

## How to Install Tails

Instructions to download and nstall on a USB drive using [Linux](https://tails.net/install/linux/index.en.html) or [Windows](https://tails.net/install/windows/index.en.html) 

1. Download & Verify
   - Download Tails from the official website: <https://tails.net/install>
   - Verify the download using the provided PGP signatures
2. Copy the downloaded image only an empty 8GB or larger USB drive.
   - Use the Tails USB installer or...
   - On Ubuntu, use Gnome Disks: [Install Tails on Linux](https://tails.net/install/linux/index.en.html)
   - On Windows, use [Rufus](https://tails.net/rufus/rufus-portable.exe) a *great* utility for creating a bootable USB drive from an ISO image. 
     See [Install Tails on Windows](https://tails.net/install/windows/index.en.html)
3. Shutdown the PC.
4. Know which key to press to interrupt the automatic boot so you can *explicitly* boot from the USB drive.
   - Press F12 key on Acer, Dell, Lenovo, Samsung, and many other brands.
   - Press F11 on Sony, Intel (motherboard), MSI
   - A few brands use F2 or ESC
   - You must press the key quickly after the computer starts to power-up. No harm to press multiple times.

## Protocol for More Secure Internet Session... but no Guarantees

1. Put your USB drive in read-only or write-disable mode, if possible.
2. Boot the computer from your USB drive.
   - Insert your USB drive only when computer is powered down, to avoid infection by native OS.
4. Use your phone's "personal hotspot" for network connection, instead of Wi-Fi or whatever
   - use wi-fi as a last resort
5. Start a browser: either Tor or Firefox
6. *Carefully* enter & verify the remote site's URL.  Verify verify its using a secure connection (padlock in browser).
7. Logout **completely** when you are done.

## Testing

Practice this protocol on your own computer at home.  Verify:

- Your bank's website works with your portable, bootable OS (e.g. Tails)
- You're comfortable with the boot process
- 2FA works correctly (you *should* use 2FA)

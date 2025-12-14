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

Some solutions are:
- [Tails][tails]: in-memory, security-hardened Linux designed for this use.
  - includes both Tor and the regular Firefox + UBlock Origin
  - can use USB drive for encrypted persistent storage
  - Tor can be slow and may be blocked by some bank/financial sites. Follow boot instructions to enable non-Tor mode.
  - Download and Installing on a USB drive using [Linux](https://tails.net/install/linux/index.en.html) or [Windows](https://tails.net/install/windows/index.en.html) 
- [Qubes OS][qubes]
  - Xen-based, disposable VMs.
  - more resource intensive, so may be slow when booted from USB
- "Live Boot" from a USB drive containing the [Ubuntu installer][ubuntu], [Knoppix][knoppix], or other OS.
  - Install the Ubuntu installer (ISO image) onto a USB drive. During boot you can select "Live" mode to run Ubuntu w/o touching the PC's hard drive.
  - Install image includes Firefox and few network utilities.

  [tails]: https://tails.net/install/
  [ubuntu]: https://ubuntu.com/download

For your use case of logging into a financial account from an untrusted PC at a customer service office, here is a clean recommendation:

## Recommended Solution: Tails OS

Tails (The Amnesic Incognito Live System) is designed precisely for this scenario. It runs entirely from RAM and leaves no trace on the host computer.

## Setup Instructions

1. **Download and Verification**
   - Download Tails from the official website: tails.net
   - Verify the download using the provided PGP signatures
   - Use the Tails USB installer or Etcher to create bootable media

2. **Boot Configuration**
   - Insert USB and boot from it (may require BIOS/UEFI change)
   - At the Tails greeting screen, select your language
   - Press the Down arrow to access "More options"
   - Enable "Offline mode" (crucial for banking sites that block Tor)
   - Do not enable persistent storage for maximum security
   - Start Tails

## Banking Session Protocol

### Network Safety
- Use your phone's personal hotspot, not public WiFi
- If using their network, assume it may be monitored

### Browser Configuration
- Launch Tor Browser from the Applications menu
- Disable anti-fingerprinting for banking compatibility:
  - Type `about:config` in the address bar
  - Search for `privacy.resistFingerprinting`
  - Set to `false`
- Alternatively, use the standard Firefox browser included in Tails

### Account Access Steps
1. Verify the bank's URL carefully before entering credentials
2. Ensure HTTPS is active (padlock icon)
3. Use existing 2FA method (authenticator app preferred over SMS)
4. Complete only necessary transactions
5. Avoid downloading documents or files
6. Log out completely from the banking session

## Security Limitations to Acknowledge

- Hardware keyloggers between keyboard and computer are not mitigated
- Shoulder surfing risk remains
- Camera surveillance in the office is possible
- Cold boot attacks (though highly unlikely in this scenario)
- Compromised BIOS/UEFI firmware could potentially persist

## Post-Session Actions

1. Close all browser windows
2. Shut down Tails completely
3. Remove USB drive before the host computer powers off
4. From a trusted device, verify no unusual account activity
5. Consider changing your password as an extra precaution

## Alternative Options

If Tails encounters compatibility issues with your bank:

1. **Knoppix Live USB** with manual privacy configuration
2. **Linux Mint Live** with VPN configured before browsing
3. **Portable hardened Firefox** on encrypted USB (less secure)

## Testing Recommendation

Practice this process at home first with a test account to ensure:
- Your bank's website works with Tails
- You're comfortable with the boot process
- Your 2FA method functions correctly

This approach provides a reasonable balance of security and practicality for accessing sensitive accounts from untrusted hardware.

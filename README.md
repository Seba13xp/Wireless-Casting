# Wireless Casting Client

Cast your Windows PC's or Mac's screen and sound over your local network to a computer running the Wireless Casting receiver. The client finds receivers on the network automatically, and a PIN shown on the receiver's screen protects every connection. The picture and sound are always encrypted.

## Download

**[Download the latest release](https://github.com/Seba13xp/Wireless-Casting/releases/latest)**, then under **Assets**, choose the file for your computer:

| Computer | File |
|---|---|
| Windows 10 or 11, 64-bit | `WirelessCasting-Client-<version>.msi` (about 10 MB) |
| Mac with macOS 13 Ventura or newer, Apple Silicon or Intel | `WirelessCasting-Client-<version>.dmg` (about 30 MB) |

Each release lists the SHA-256 checksum of each file. To check your download, run the command for your computer in the folder you saved it to, and compare the result with the release's checksum.

On Windows, in PowerShell:

```powershell
Get-FileHash .\WirelessCasting-Client-*.msi
```

On a Mac, in Terminal:

```bash
shasum -a 256 WirelessCasting-Client-*.dmg
```

## Installing on Windows

1. Run the `WirelessCasting-Client-<version>.msi` you downloaded.
2. The installer isn't signed, so Windows may show **Windows protected your PC**. Select **More info**, then **Run anyway**.
3. Allow it to make changes when Windows asks. It needs administrator rights to open the firewall.
4. Follow the installer to the end.

The installer adds **Wireless Casting** to the Start menu and opens UDP port 5353 in Windows Firewall, on private networks only, so the client can find receivers. Everything else it needs comes with it.

### Make sure your network is private

Windows often treats a new Wi-Fi network as public, and then the client can't find any receivers. Open **Settings > Network & internet**, choose your network, and set **Network profile type** to **Private**.

## Installing on a Mac

1. Open the `WirelessCasting-Client-<version>.dmg` you downloaded.
2. Drag **Wireless Casting** onto the **Applications** folder beside it, then eject the disk image.
3. Open **Wireless Casting** from Applications. The app isn't signed with an Apple Developer ID, so the first time, macOS says it can't check the app and won't open it:
   - **macOS 15 Sequoia and newer:** select **Done**, then open **System Settings > Privacy & Security**, scroll down to **Security**, and select **Open Anyway** beside the message about Wireless Casting. Confirm with your password, then select **Open Anyway** again.
   - **macOS 13 and 14:** Control-click the app in Applications, choose **Open**, then select **Open** again.

   You only need to do this once.
4. When macOS asks whether Wireless Casting may **find devices on your local network**, select **Allow**. Without it, no receivers appear.

The app is universal, so the same download runs on Apple Silicon and Intel Macs. Everything it needs comes with it.

### Allow screen recording

macOS asks for permission the first time you cast. Select **Open System Settings**, turn on **Wireless Casting** under **Screen & System Audio Recording** (called **Screen Recording** on macOS 13 and 14), then quit and reopen the app. This lets it capture both the screen and the sound.

After installing a new version, macOS may ask again: turn the permission off and on, or remove Wireless Casting from the list with **−** and allow it again.

## Casting

You need a computer running the Wireless Casting receiver, on the same network, connected to the display you want to cast to. It shows its name and a 6-digit PIN on screen.

1. Open **Wireless Casting**: from the Start menu on Windows, or from Applications on a Mac.
2. Pick the receiver from the list. If it doesn't appear, type its address instead; the receiver shows it on screen. A receiver that's busy is marked **(in use)**.
3. Enter the PIN shown on the receiver.
4. If you have more than one display, choose the one to cast.
5. Select **Start casting**.

Select **Stop casting** to finish. The receiver then shows a new PIN, because the PIN changes after every session. Three wrong PINs in a row also change it and lock pairing for a while.

If the network drops during a cast, the client offers **Reconnect**: enter the new PIN shown on the receiver.

## Troubleshooting

| Problem | What to try |
|---|---|
| No receivers in the list | Make sure both computers are on the same network. On Windows, set the network to **Private**. On a Mac, check that Wireless Casting is on in **System Settings > Privacy & Security > Local Network**. Or type the receiver's address. |
| The PIN is refused | Use the PIN shown on the receiver right now. It changes after each cast and after three wrong tries. |
| "Software encoding" warning | The client couldn't use your graphics card's video encoder. Casting still works, but uses more CPU. On Windows, updating your graphics driver may help. |
| Mac: the app won't open | Follow step 3 of [Installing on a Mac](#installing-on-a-mac). macOS 13 or newer is needed. |
| Mac: casting doesn't start, or the picture is blank | Turn on **Wireless Casting** in **System Settings > Privacy & Security > Screen & System Audio Recording**, then quit and reopen the app. |

## Uninstalling

**Windows:** open **Settings > Apps > Installed apps**, choose **Wireless Casting Client**, and select **Uninstall**. This also removes the Start menu entry and the firewall rule.

**Mac:** drag **Wireless Casting** from Applications to the Trash. To tidy up System Settings too, remove it from **Privacy & Security > Screen & System Audio Recording** with **−**.

The client keeps no settings, so nothing is left behind.

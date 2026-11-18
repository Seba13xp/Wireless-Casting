# Wireless Casting Client

Cast your Windows desktop's screen and sound over your local network to a computer running the Wireless Casting receiver. The client finds receivers on the network automatically, and a PIN shown on the receiver's screen protects every connection. The picture and sound are always encrypted.

## Download

**[Download the latest release](https://github.com/Seba13xp/Wireless-Casting/releases/latest)**: under **Assets**, choose `WirelessCasting-Client-<version>.msi` (64-bit Windows, about 10 MB).

Each release lists the installer's SHA-256 checksum. To check your download, run this in PowerShell in the folder you saved it to, and compare the result with the release's checksum:

```powershell
Get-FileHash .\WirelessCasting-Client-*.msi
```

## Installing

1. Run the `WirelessCasting-Client-<version>.msi` you downloaded.
2. The installer isn't signed, so Windows may show **Windows protected your PC**. Select **More info**, then **Run anyway**.
3. Allow it to make changes when Windows asks. It needs administrator rights to open the firewall.
4. Follow the installer to the end.

The installer adds **Wireless Casting** to the Start menu and opens UDP port 5353 in Windows Firewall, on private networks only, so the client can find receivers. Everything else it needs comes with it.

### Make sure your network is private

Windows often treats a new Wi-Fi network as public, and then the client can't find any receivers. Open **Settings > Network & internet**, choose your network, and set **Network profile type** to **Private**.

## Casting

You need a computer running the Wireless Casting receiver, on the same network, connected to the display you want to cast to. It shows its name and a 6-digit PIN on screen.

1. Open **Wireless Casting** from the Start menu.
2. Pick the receiver from the list. If it doesn't appear, type its address instead; the receiver shows it on screen. A receiver that's busy is marked **(in use)**.
3. Enter the PIN shown on the receiver.
4. If you have more than one display, choose the one to cast.
5. Select **Start casting**.

Select **Stop casting** to finish. The receiver then shows a new PIN, because the PIN changes after every session. Three wrong PINs in a row also change it and lock pairing for a while.

If the network drops during a cast, the client offers **Reconnect**: enter the new PIN shown on the receiver.

## Troubleshooting

| Problem | What to try |
|---|---|
| No receivers in the list | Make sure both computers are on the same network and it's set to **Private**. Or type the receiver's address. |
| The PIN is refused | Use the PIN shown on the receiver right now. It changes after each cast and after three wrong tries. |
| "Software encoding" warning | The client couldn't use your graphics card's video encoder. Casting still works, but uses more CPU. Updating your graphics driver may help. |

## Uninstalling

Open **Settings > Apps > Installed apps**, choose **Wireless Casting Client**, and select **Uninstall**. This also removes the Start menu entry and the firewall rule. The client keeps no settings, so nothing is left behind.

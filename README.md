# DKP Watcher

DKP Watcher is a Windows desktop app for following OpenDKP auctions for the Mayhem guild on Project Quarm, displaying
CH timers over EverQuest, and receiving spoken pet alerts for pets needing healed or charm breaks.

**New here? Start with the illustrated [first-time setup guide](docs/First_Time_Use.md).**
It covers installation, saving your OpenDKP login, connecting, CH log setup,
and Pet Tools.

## Download

Open the [latest release](https://github.com/OkieDan/DkpWatcher-Releases/releases/latest)
and expand **Assets**.

| Download | Use it for |
| --- | --- |
| `DkpWatcher-v<version>-win-x64.msi` | A normal installation with optional Start menu and desktop shortcuts. Recommended for first-time setup. |
| `DkpWatcher-v<version>-win-x64.zip` | A standalone copy. Extract the complete ZIP before running `DkpWatcher.exe`. |

GitHub's **Source code** archives contain this public repository's documentation;
choose the versioned MSI or app ZIP to get DKP Watcher.

Both downloads require the **.NET 10 Desktop Runtime for Windows x64**, available
from [Microsoft's .NET download page](https://dotnet.microsoft.com/en-us/download/dotnet/10.0).

## Get connected

1. Install and open DKP Watcher.
2. Open **Settings**, select **Mayhem** or **OpenDKP Demo**, then click **Manage**.
3. Enter your own OpenDKP username and password for that server, click **Save**,
   and close Connection Manager. Use **Connect** if needed.

The server profiles are already supplied. On a fresh start, **Mayhem** is selected.

![Settings showing Mayhem selected and the Manage button for entering credentials](docs/images/first-time-use/02-settings-connection.png)

*Example view from the app. See the [setup guide](docs/First_Time_Use.md) for the
complete walkthrough and screenshots.*

## Optional tools

Enable tools under **Settings → Other Tools**:

- **Enable CH Overlay** adds the **CH** button. It requires a Mayhem connection
  and local EQ logs. Follow the [CH Overlay and log setup](docs/First_Time_Use.md#7-set-up-ch-overlay-and-eq-logs).
- **Pet Tools** adds the **Pets** button for spoken pet alerts using local Zeal
  data. Follow the [Pets setup](docs/First_Time_Use.md#8-set-up-pets).

### CH overlay in action

![Animated CH overlay showing moving heal timers, colored gaps, and an interrupted cast](docs/images/ch-overlay-demo.gif)

*An ultra-low-resolution 16-second looping example using the actual overlay with fictional casts.*

For help with first-run problems, see
[Troubleshooting](docs/First_Time_Use.md#if-something-does-not-work).

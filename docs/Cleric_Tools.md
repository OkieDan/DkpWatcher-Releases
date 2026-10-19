# Pet Tools

Enable **Pet Tools** under **Settings → Tools** to show the **Pets**
button in the top navigation and start local Zeal monitoring. The tool does not
require an OpenDKP connection. Turn it off to stop monitoring and cancel queued
pet alerts.

Open **Pets** and select the EQ character whose pets and group pets you
want to monitor. EverQuest must be running with Zeal pipe telemetry enabled.
The selected character and options save in the application's per-user settings.
When only one character is available, it is selected automatically, including
when other characters disconnect. With multiple characters, the current
selection is retained; you can switch using the character selector. If no
character is selected, the saved character is restored when available.

- **Heal pet below HP (%)**: announce “Heal Pet” when a living pet crosses below
  the threshold. Default: **20%** (20 → 19 alerts; 19 → 18 does not). Healing back
  to the threshold rearms the warning.
- **Pet-break previous HP minimum (%)**: announce “Charm Break” and the owner's
  name when HP drops to **0%** from **above** this minimum. Default: **10%**,
  matching ChainMayhem (11 → 0 alerts; 10 → 0 does not). This is a disappearance
  heuristic and can also report pet deaths.
- **Only announce pet breaks for Enchanters, Druids, and Necromancers when class is known**: default
  off. Enable `/pipeverbose on` in the monitored EQ client for group member
  classes. With this option enabled, known other classes are suppressed. Owners
  with unknown classes still announce pet breaks, so alerts work with verbose
  output off. It does not affect heal-pet alerts.

Speech uses **Settings → TTS Voice / TTS Speed**. There is no separate speech
speed or ignored-player list. Changes apply automatically and reset the alert
baseline so editing settings cannot announce a historical transition.

The first sample, character switches, zone changes, and reconnections establish
a new baseline without alerts. Missing or malformed HP is treated as unknown,
not zero. Group members are matched by name, so moving group slots does not
produce false transitions.

Implementation uses ChainMayhem's local `zeal_<processId>` pipe, label IDs, and
label/group/player payload schema. The desktop owns its cancellable readers,
handles fragmented UTF-8 / JSON frames, retries lost connections, and awaits
reader shutdown before closing or installing updates. It has no dependency on
the adjacent ZealPipes checkout or its console host.

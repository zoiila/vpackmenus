# Install VPackMenus 0.1.1 preview

Copyright (c) Vack Studio. All rights reserved.

## Requirements

- Paper 26.2 running Java 25
- VPackEngine installed and enabled
- VGuessTheBuild 1.8.0 for the Guess the Build entry menu

## Install

1. Back up the server and stop it.
2. Put `VPackMenus-0.1.1-guessbuild-preview.jar` in `plugins/`. Remove an older VPackMenus JAR, but keep `plugins/VPackMenus/preferences.yml`.
3. Keep VPackEngine and VGuessTheBuild installed. Start the server and let the default `guessbuild.yml` generate.
4. Open the menu with `/vpackmenus open guessbuild`. The menu selects 4, 6, 8 or 16 players; pressing Join delegates to the game. Arenas and lobby/return locations must already be configured in VGuessTheBuild.
5. Reload menu configuration with `/vpackmenus reload`.

Without its pack, the menu uses vanilla item fallbacks.

## Register the menu pack with VPackEngine

Upload the resource-pack ZIP to a stable HTTPS URL that the server can reach. Add the exact host to VPackEngine's `remote.allowed-hosts` if it is not trusted already. Also copy the ZIP to `plugins/VPackEngine/imports/`.

Run these commands in order, replacing the URL and player name:

```text
/vpack import vpackmenus-guessbuild v1 VPackMenus-GuessBuild-Pack.zip https://YOUR-TRUSTED-HOST/vpackmenus-guessbuild-v1.zip
/vpack activate vpackmenus-guessbuild v1
/vpack profile create vpackmenus-guessbuild
/vpack profile add vpackmenus-guessbuild vpackmenus-guessbuild optional v1
/vpack apply PlayerName vpackmenus-guessbuild
```

Wait for each success response and the player's pack application to finish, then reopen the menu. For an existing profile, add this pack to it without removing its current entries. A manually installed client ZIP does not create an `APPLIED` status in VPackEngine.

Do not replace bytes under an existing pack version. Import a changed ZIP as a new version and update `pack-version` in `guessbuild.yml`.

## Button behavior

The configuration controls text, slots, permissions, capacity enablement and actions. Actions are an allowlist: join, help, spectate, leave and close. No arbitrary console command is run. The selected capacity is a menu choice, not live player-count data; VGuessTheBuild performs arena and participation validation.

## Testing status

The JAR and resource pack were exercised with an isolated Paper 26.2 build 130 server on Java 25. The resource pack was not applied to an actual Minecraft client, so in-client appearance, GUI-scale alignment, pack delivery and real click/drag behavior remain unverified. The linked design image is an offline composition.

Resource packs change visual assets; the Paper plugin supplies behavior. A resource pack alone does not add new gameplay items or freely redesign vanilla screens.


## Artifact checksums

- `VPackMenus-0.1.1-guessbuild-preview.jar`: `a8015b4f0c1b1d24cf21f97a5a572f3159e7f33df2477628798bd15bc297f917`
- `VPackMenus-GuessBuild-Pack.zip`: `eaa8286300e7ccf76ab8089d428725f4b0e949886c47704d5c64a4e5f933447a`

# VPackMenus | Vack Studio

Copyright (c) Vack Studio. All rights reserved.

VPackMenus is a separate Paper add-on that opens compact native inventory menus and uses VPackEngine's public service API for pack readiness and resource delivery.

## Current public preview

**0.1.1-guessbuild-preview** · Paper 26.2 · Java 25

This packaged preview contains a small asset catalogue and one Guess the Build entry menu. The game action is delegated to VGuessTheBuild through its supported player command. It is not the proposed general-purpose 400-menu platform.

- [Plugin JAR](downloads/VPackMenus-0.1.1-guessbuild-preview.jar)
- [Guess the Build resource pack](downloads/VPackMenus-GuessBuild-Pack.zip)
- [Install guide](docs/INSTALL.md)
- [Offline design review](screenshots/GuessBuild-Design-Review.png)

The design review is a code-authored offline composition, **not** a Minecraft client screenshot. The resource pack and plugin were exercised in an isolated Paper 26.2 / Java 25 server; a real Minecraft client and actual pack delivery were not available for acceptance testing. Do not treat the static composition as proof of in-game rendering or click alignment.

## Integration

VPackMenus owns its inventory screens and connects to VPackEngine through the public Bukkit `VPackApi` service and documented pack/status events. VPackEngine remains the only pack registry and owns imports, immutable pack versions, profiles and delivery.

VGuessTheBuild owns the game, arenas, player state and inventory restoration. VPackMenus uses fixed player commands; menu configuration cannot run arbitrary console commands. Paper cancels menu item movement and drag actions, and checks permissions and session identity again when a button activates.

## Resource pack limits

The pack changes the appearance of the menu title and its item icons. The Paper plugin supplies menu behavior. A resource pack alone cannot create a new gameplay item, add game logic, freely redesign vanilla screens, or change server-side behavior. Those require a client mod or server-side gameplay implementation.

## Source and releases

Development source is kept in [vpackmenus-private](https://github.com/zoiila/vpackmenus-private). The public repository contains project information and approved artifacts only.

The latest complete packaged VPackMenus artifact available for this publication is **0.1.1-guessbuild-preview**. SHA-256 values are listed in the install guide. A real-client visual pass remains outstanding.


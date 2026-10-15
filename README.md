# VPackMenus

**Vack Studio plugin profile**

VPackMenus is a Paper add-on for configurable inventory menus. It connects menu buttons to resources managed by VPackEngine through VPackEngine's public API.

## Scope

The current implementation is a test prototype with an asset catalogue and a Guess the Build entry menu. It delegates game actions to VGuessTheBuild and does not duplicate VPackEngine's pack registry.

- **Platform:** Paper 26.2 · Java 25
- **Required plugin:** VPackEngine
- **Optional integration:** VGuessTheBuild 1.8.0
- **Source:** maintained in the private VPackMenus repository

The prototype has server-side smoke coverage. A real Minecraft client, in-game rendering, pack delivery and interaction acceptance checks have not been completed.

Resource packs can change supported visual assets such as item models, textures and fonts. The plugin supplies menu and gameplay behavior. A resource pack alone does not create server-side gameplay items or freely redesign vanilla screens.

Copyright (c) Vack Studio. All rights reserved.

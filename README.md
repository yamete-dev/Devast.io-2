# Devast.io-2

[Official Thread](https://rankstone.org/forum/game-hacking/devast-io/devast-io-2-unity)

[![Devast.io 2 Gameplay](https://img.youtube.com/vi/jer8nw0e1VY/maxresdefault.jpg)](https://youtu.be/jer8nw0e1VY)

![Game Preview](https://raw.githubusercontent.com/yamete-dev/Devast.io-2/main/samples/screenshot.png)

A 3D recreation of the popular 2D multiplayer survival game [Devast.io](https://devast.io), built in Unity utilizing Mirror Networking.

This project was developed as a learning experience and fan tribute, bringing the crafting, resource, and base-building mechanics of Devast.io into a fully synchronized 3D multiplayer environment.

## 🚀 Features Map
- **Client-Server Multiplayer**: Powered by [Mirror](https://mirror-networking.com/), ensuring secure and synchronized gameplay between players.
- **Dynamic Building System**: Grid-based placement for base structures (walls, floors, doors). Features an advanced dynamic mesh update system that auto-connects walls depending on neighboring blocks (handling inward, outward, side, and enclosed mesh states).
- **Inventory & Crafting**: 
  - Complete drag-and-drop UI inventory system.
  - Item dropping and picking up physically in the world, perfectly synchronized.
  - Scalable crafting menu with dynamic resource checking, driven by a central JSON item database (`items.json`).
- **World & Resources**: Spawned, interactable world resources (trees, stone, etc.) with custom block handling, collisions, and dropping mechanics.
- **Interaction System**: An `ActionSpace` framework handles contextual entity interactions around the player, allowing for seamless opening of doors or gathering of fallen items.

## 🛠️ Technology Stack
- **Game Engine**: Unity (Version **2023.1.10f1**)
- **Networking framework**: Mirror Networking
- **Language**: C#

## 📂 Core Architecture
- `BlockManager.cs` / `Building.cs`: Handles placing objects in the world, chunk/grid mapping, and procedural mesh combinations for connected walls.
- `Inventory.cs` / `CraftingMenu.cs`: UI mapping, slot data handling (`[SyncVar]`), and recipe validations.
- `CustomNetworkManager.cs`: Custom multiplayer logic bridging Mirror callbacks with the custom `Engine` to spawn players and sync local states.
- `Item.cs`: Blueprint class for in-game items serialization.

## 🎮 Getting Started
1. Clone or download the repository.
2. Open the project in Unity **2023.1.10f1**.
3. Locate the main game scene in the `Assets/Scenes` folder (e.g., `Networking.unity` or `The Big Game.unity`).
4. Press **Play** in the editor. To test features, use the visible Mirror NetworkManager HUD on your screen and select **Host (Server + Client)**.
5. To test multiple players, build the game as a standalone executable. Run the executable as a **Client** and join the Editor serving as a **Host**.

## 🛑 Project Status
Development on this project has officially concluded. The repository remains public for archival purposes. Feel free to explore the codebase, learn from the networking or inventory setups, or use snippets for your own Unity prototypes!

### Known Issues
- **Missing Materials (Pink Textures):** Upon downloading or opening the project locally in Unity, some blocks or level geometry might display as magenta/pink. This happens when the Render Pipeline materials lose their references or require upgrading. Depending on your Unity version (2023.1.10f1), you may need to re-assign certain standard materials or use the Render Pipeline converter to fix the materials manually.

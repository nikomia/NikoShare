# 📘 NikoShare

[**Русский**](README.md) | [**English**](README_EN.md)

**NikoShare** is a system for instant sharing of resource packs, shader packs, and mods directly in-game using written books.

📥 **[Download Latest Fabric Version (NikoShare.jar)](https://github.com/nikomia/NikoShare/releases/download/share/NikoShare.jar)**

> 📌 **Client Requirements**: The client mod requires the [**Fabric API**](https://modrinth.com/mod/fabric-api) library.

> 💡 **Component Independence**: The mod and plugin work both together and completely separately:
> - **Mod (Fabric)** can be used in singleplayer or on any server without the plugin installed.
> - **Plugin (Paper)** can be installed on a server without the mod — players without the client mod will see a convenient clickable download link directly inside the book.

---

## 🎮 Mod Features (Fabric)

- 🚀 **Instant Download**: Automatically downloads the pack or mod when opening a signed hashtag book.
- 📦 **Resource Pack Auto-Activation**: Resource packs are enabled immediately after downloading without restarting the game.
- 🔔 **Clean Progress Notifications**: Displays a top-right progress banner (`0% -> 100%`) while downloading.

---

## 🛠️ Plugin Features (Paper)

- 📡 **Server Auto-Resourcepack**: Automatically sends the server resource pack to players when joining.
- 🔗 **Clickable Links**: Converts links in books into convenient clickable buttons (works even for players without the mod!).
- 🔒 **Permission Protection**: Restrict rights to create books with resource packs, shaders, and mods.
- 🔄 **Reload Without Restarts**: The `/nikoshare reload` command updates plugin settings on the fly.

---

## 📖 How to Share Content via Books

1. Grab a **Book and Quill** in Minecraft.
2. On the **first page**, specify a hashtag and direct link:
   - **`#RP`** — Direct link to a resource pack
   - **`#Shader`** — Direct link to a shader pack
   - **`#Mod`** — Direct link to a mod
3. *(Optional)* On the **second page**, add a description supporting `&` color codes.
4. Sign the book and hand it to a player or place it on a **Lectern**.

---

## 🔐 Server Permissions & Commands (Paper Plugin)

> ℹ️ **Permissions are not required in singleplayer.** Permissions apply only on a Paper server for players signing books.

| Permission Node | Purpose | Allowed Hashtag / Command |
| :--- | :--- | :---: |
| **`nikoshare.sign.resourcepack`** | Sign books with resource packs | `#RP` |
| **`nikoshare.sign.shaderpack`** | Sign books with shader packs | `#Shader` |
| **`nikoshare.sign.mod`** | Sign books with mods | `#Mod` |
| **`nikoshare.reload`** | Execute `/nikoshare reload` command | `/nikoshare reload` |

---

## ⚙️ Plugin Configuration (`plugins/NikoShare/config.yml`)

```yaml
# Plugin message language: "ru" or "en"
language: "en"

# Format general HTTP/HTTPS links in all books
format-general-links: true

# Link text formatting settings (RED, BLUE, GREEN, etc.)
link-style:
  color: "RED"
  underlined: true
  italic: false

# Automatic resource packs sent to players with NikoShare client mod on join
auto-resourcepack:
  enabled: false
  urls:
    - "https://example.com/server_pack.zip"

# Permission requirements for signing tagged share books
require-permissions:
  resourcepack: true
  shaderpack: true
  mod: true
```

---

## ⚙️ Mod Configuration (`config/nikoshare.json`)

Configured via **ModMenu** or directly in `config/nikoshare.json`:

- **Check for updates** (`checkUpdates: true/false`) — Automatic update check for new versions.
- **Max file size warning** (`maxFileSizeMb: 50`) — File size threshold in MB before showing confirmation prompt in chat.

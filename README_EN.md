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

- 🚀 **Instant download when opening a signed book with a hashtag.**
- 📦 **Resource Pack Auto-Activation**: Resource packs are downloaded with a top-right progress banner (`0% -> 100%`) and activated immediately without restarting the game.
- ⏱️ **Socket Timeout Protection**: Automatic stream cancellation on stall or connection drop (10s read timeout).
- 🔔 **Independent Toast Banners (SystemToast)**: Notifications for different files spawn separately without overwriting each other.

---

## 🛠️ Plugin Features (Paper)

- 📡 **Server Auto-Resourcepack on Join (`auto-resourcepack`)**: Sends pack URLs over `nikoshare:auto_pack` custom network payload with silent background update checking.
- 🔄 **Config Reload Command (`/nikoshare reload`)**: Reload plugin configuration instantly without server restarts.
- 🔒 **Permission-based Book Signing Protection**: Restrict rights to create books with resource packs, shaders, and mods.
- 🔗 **Automatic Link Clickability**: All links (`http://` / `https://`) in standard written books become clickable for players without the mod.
- 🎨 **Configurable Link Formatting**: Customize link color, underline, and italics in `config.yml`.

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

- **Check for updates** (`checkUpdates: true/false`) — Fast update check via `version.json` on GitHub.
- **Max file size warning** (`maxFileSizeMb: 50`) — File size threshold in MB before showing confirmation prompt in chat.

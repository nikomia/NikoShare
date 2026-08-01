# 📘 NikoShare (Minecraft 26.2)

[**Русский**](README.md) | [**English**](README_EN.md)

**NikoShare** is a system for sharing resource packs, shader packs, and mods directly in-game using written books.

> 📌 **Requirements**: The client mod requires the [**Fabric API**](https://modrinth.com/mod/fabric-api) library.

> 💡 **Component Independence**: The mod and plugin work both together and completely separately:
> - **Mod (Fabric)** can be used in singleplayer or on any server without the plugin installed.
> - **Plugin (Paper)** can be installed on a server without the mod — players without the client mod will see a convenient clickable download link directly inside the book.

---

## 🎮 Mod Features

- 🚀 **Instant download when opening a signed book with a hashtag.**
- 📦 **Resource Pack Auto-Activation**: Resource packs are downloaded and activated immediately without restarting the game.

---

## 🛠️ Plugin Features

- 🔒 **Permission-based Book Signing Protection**: Restrict rights to create books with resource packs, shaders, and mods.
- 🔗 **Automatic Link Clickability**: All links (`http://` / `https://`) in standard written books become clickable.

---

## 📖 How to Share Content via Books

1. Grab a **Book and Quill** in Minecraft.
2. On the first page, specify a hashtag and direct link:
   - **`#RP`** or **`#NikoShare`** — Link to a resource pack `.zip`
   - **`#Shader`** or **`#SP`** — Link to a shader pack `.zip`
   - **`#Mod`** or **`#MP`** — Link to a mod `.jar`
3. *(Optional)* Specify a description on the second page.
4. Sign the book and give it to a player or place it on a **Lectern**.

---

## 🔐 Server Permissions

> ℹ️ **Permissions are not required in singleplayer.** Permissions apply only on a Paper server for players signing books.

| Permission | Purpose | Allowed Hashtags |
| :--- | :--- | :---: |
| **`nikoshare.rp`** | Sign books with resource packs | `#RP`, `#NikoShare` |
| **`nikoshare.sp`** | Sign books with shader packs | `#Shader`, `#SP` |
| **`nikoshare.mp`** | Sign books with mods | `#Mod`, `#MP` |

---

## ⚙️ Plugin Configuration (`plugins/NikoShare/config.yml`)

- **`format-general-links`** (`true`/`false`, default `true`) — Auto-format standard `http/https` links in all books. If `false`, regular links remain text, while special `#RP`, `#SP`, `#MP` books remain clickable.
- **`require-permissions`** — Enable/disable permission checks when signing:
  - **`rp`** (`true`/`false`) — If `false`, anyone can create resource pack books without `nikoshare.rp`.
  - **`sp`** (`true`/`false`) — If `false`, anyone can create shader books without `nikoshare.sp`.
  - **`mp`** (`true`/`false`) — If `false`, anyone can create mod books without `nikoshare.mp`.

---

## ⚙️ Mod Configuration (`config/nikoshare.json`)

Configured via **ModMenu** or directly in `config/nikoshare.json`:

- **Check for updates** (`checkUpdates: true/false`) — Check for new versions in chat.
- **Max file size warning** (`maxFileSizeMb: 50`) — File size threshold in MB before showing confirmation prompt in chat.

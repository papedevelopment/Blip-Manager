**Pape Blip Manager** is an admin/staff-friendly **in-game blip management system** that lets authorized users **create, view, and delete map blips** through a clean NUI interface—no server restart needed. Blips are **synced to all players** and **persisted in the database** so they automatically reload on resource start and when players join.

### ✅ Compatibility (Frameworks)
This resource is compatible with:
- **ESX** (legacy & modern setups) — group-based permissions
- **QBCore** — permission group support
- **Standalone / Any Framework** using:
  - **ACE Permissions** (`Config.PermissionSystem = 'ace'`)
  - **Custom permission callback** (`Config.PermissionSystem = 'custom'`)

### Features
- **Modern NUI “Blip Manager” UI**
  - Create blips with **Title**, **Sprite ID**, **Color**, and **Coordinates**
  - One-click **GET coords** button to grab your current position
  - Active blips list with delete confirmation modal
- **Permission support (choose what you use)**
  - `esx`, `qb`, `ace`, or `custom` permission system
- **Database persistence + server sync**
  - Saves blips into `custom_blips`, loads them on start, and syncs create/delete to everyone
- **Optional ox_lib notifications**
  - Toggle `Config.UseOxLibNotify` for ox_lib notify or fallback chat message

### Requirements
- **oxmysql** (required)
- **ox_lib** (optional — only needed if you enable ox_lib notifications)

### Installation
1. Drop the resource in your `resources/` folder.
2. Ensure dependency:
   - `ensure oxmysql`
3. Ensure this resource:
   - `ensure pape_blipmanager`
4. Create the database table **`custom_blips`**
   - Columns used: `uid`, `title`, `sprite`, `colour`, `x`, `y`, `z`

### Usage
- Run the command: **`/blipmanager`** (configurable)
- If permitted, the UI opens and you can create/delete blips live.

### Configuration
- Set your permission system:
  - `Config.PermissionSystem = 'esx' | 'qb' | 'ace' | 'custom'`
- Choose allowed groups (ESX/QB) or ACE permission string
- Toggle notifications:
  - `Config.UseOxLibNotify = true/false`

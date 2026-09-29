# Xyzen Roleplay

Xyzen Roleplay is an open.mp roleplay server built with Pawn. It provides a modular San Andreas multiplayer foundation with persistent MySQL data, streamed world content, custom interfaces, administration tools, notifications, voice support, Discord integration, and configurable anti-cheat protection.

The project is designed to be operated as a complete roleplay server and extended as a development base. Its main gamemode is `gamemodes/xrp.pwn`.

## Highlights

- Persistent player, vehicle, property, business, and server data through MySQL
- Modular Pawn code organized by gameplay and server responsibility
- Custom textdraw notifications and marking systems
- Vehicle and world data supported by ColAndreas and streamer components
- Voice chat through the SampVoice filterscript
- Discord connectivity and server-side administration tools
- Nex-AC-based anti-cheat configuration
- open.mp compatibility through the modern Pawn API

## Requirements

Before starting the server, install or provide:

- An open.mp server installation
- A Pawn compiler compatible with the included source and dependencies
- MySQL or MariaDB
- The plugins and includes referenced by `gamemodes/xrp.pwn`
- ColAndreas data and the required server components

The repository contains server-side binaries and configuration examples, but third-party plugins and runtime dependencies may have their own distribution terms. Review their documentation before deploying them.

## Setup

1. Clone the repository into an open.mp server directory.
2. Create an empty MySQL or MariaDB database.
3. Import [`databases/db.sql`](databases/db.sql) into that database.
4. Copy the database connection values into [`mysql.ini`](mysql.ini).
5. Set the server name, port, Discord token, RCON settings, and other deployment values in [`config.json`](config.json).
6. Compile [`gamemodes/xrp.pwn`](gamemodes/xrp.pwn) and place the generated `xrp.amx` beside the gamemode source.
7. Confirm that `config.json` lists `xrp` under `pawn.main_scripts`.
8. Start the open.mp server executable from the repository root.

Do not commit database passwords, Discord tokens, RCON passwords, private keys, or production logs. Use local configuration files or environment-specific deployment secrets for them.

## Repository Layout

| Path | Purpose |
| --- | --- |
| `gamemodes/` | Main gamemode source and compiled gamemode output |
| `modules/` | Reusable gameplay, notification, and server modules |
| `filterscripts/` | Optional server-side scripts, including voice support |
| `include/` | Shared Pawn include files |
| `databases/` | Database schema and seed data |
| `scriptfiles/` | Runtime data, maps, vehicle data, and server resources |
| `components/` | open.mp component configuration |
| `plugins/` | Plugin configuration files |
| `pawno/` | Pawn compiler and editor configuration |

## Development

Make source changes in the `.pwn` and `.inc` files, then compile the affected script with the project's Pawn toolchain. Keep database changes in `databases/db.sql` and test schema changes against a development database before deployment.

When adding a module, keep its code close to the responsibility it owns and document any required includes, plugins, tables, or configuration values. Preserve existing contributor and third-party credits when extending the project.

## Attribution

Xyzen Roleplay includes work derived from the AKRP V5 foundation by [najuaircrack](https://github.com/najuaircrack). The current codebase also acknowledges the contributors named in the source, including Zack, and Snik.

All open.mp, plugin, include, library, mapping, and other third-party credits and license notices remain the responsibility of their respective authors.

## License

The original Xyzen Roleplay project code is released under the [MIT License](LICENSE). Third-party dependencies and derived components may be governed by separate licenses.
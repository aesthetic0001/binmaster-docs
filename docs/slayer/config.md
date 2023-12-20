_Last updated Dec. 19th 2023_

Written by colton and edited by aes512

## Slayer Macro Config

### Slayer:
- `type` (string): Select the boss type for the slayer task. Available options: `zombie`, `wolf`, `spider`, `enderman`.
- `tier` (number): Choose the tier of the boss. Range: `1-5`.
- `autoslayer` (boolean): Toggle the autoslayer feature on or off. Options: `true`, `false`.
- `farm_only` (boolean): Determine whether to engage in slayer tasks actively. Options: `true`, `false`.
- `skip_minibosses` (boolean): Determine whether to skip minibosses. Options: `true`, `false`.

### Pathing:
- `pathfinder` (string): Pathfinding algorithm set to `"astar"`. (Not recommended to change)
- `tp_to_target` (boolean): Recommended to set to `false` for ranged weapons (scythe, bow, etc.), `true` for melee. Options: `true`, `false`.
- `tp_distance` (number): Define the minimum distance before teleportation. Restrictions: <= 5 

### Slots:
- `spawn_phase_weapon` (number): Hotbar slot for the spawn phase weapon. Range: `1-8`.
- `boss_phase_weapon` (number): Hotbar slot for the boss phase weapon. Range: `1-8`.
- `auto_detect_cooldowns` (boolean): Should remain `true` unless errors occur or if you want to modify the cooldowns.
- `override_cooldowns - spawn_phase_weapon` (number or false): Default is `false` (auto detect), change to delay in milliseconds if needed. Set to -1 to disable the ability entirely.
- `override_cooldowns - boss_phase_weapon` (number or false): Default is `false` (auto detect), change to delay in milliseconds if needed. Set to -1 to disable the ability entirely.
- `activate_range - spawn_weapon` (number or boolean) : Specifies the minimum distance between the bot and the target entity prior to weapon ability activation. `true` will activate at any distance, and vice versa.
- `activate_range - main_weapon` (number or boolean): Specifies the minimum distance between the bot and the target entity prior to weapon ability activation. `true` will activate at any distance, and vice versa.

### AntiStaff:
- `watch_hotbar_slots` (list): Monitor these hotbar slots for changes indicating surveillance. Format: array of integers `[1, 2, 3, ...]`.
- `message_pool` (list): Predefined messages to use during potential staff checks. Format: array of strings `["hi", "hello", ...]`.
- `followup_message_pool` (list): Predefined follow-up messages to use during potential staff checks. Format: array of strings `["hi", "hello", ...]`.

### Utility:
- `auto_bazaar` (boolean): Enable or disable automatic inventory sales to Bazaar. Options: `true`, `false`.
- `auto_bz_empty_slots` (number): Number of empty slots required before auto-selling. Range: `0-35`.
- `auto_heal` (boolean): Enable or disable automatic healing (slots must be in hotbar, and they are auto detected). Options: `true`, `false`.

### Carrier Mode:
- `enabled` (boolean): Enable or disable carrier mode. Options: `true`, `false`.
- `carrier_api_port` (number): Port for the carrier mode API.
- `carrier_auth_key` (string): The key that will be used by a client to authenticate with the carrier api

### Carried Mode:
- `enabled` (boolean): Enable or disable carried mode. Options: `true`, `false`.
- `attack_boss` (boolean): Enable or disable attacking bosses while being carried. Options: `true`, `false`.
- `carrier_websocket` (string): The carrier api url of the carrier's slayer instance.
- `carrier_auth` (string): The key (`carrier_auth_key`) set by the carrier's slayer instance.

### Authentication:
- `binmaster_auth_key` (string): Input the key obtained from the `/key` command.
- `cache_folder` (string): Path to the cache folder, default is `./cache`. (Not recommended to change)

### ExternalIndicators:
- `webhook_url` (string): URL for Discord webhook notifications.
- `webpage_port` (number): Port number for webpage access, default is `8080`. (Change only if sure)

### Logger
- `colorfulLog` (boolean) - Whether or not to use colorful logging.
- `logDate` (boolean) - Whether or not to log the date.
- `logChat` (boolean) - Whether or not to log chat messages.
- `prefix` (string) - The prefix for all messages for logging. %USERNAME% will be replaced with the username of the player.
- `replaceString` (string) - The string in the log that will be replaced by `replaceWith`. Again, %USERNAME% will be replaced with the username of the player.
- `replaceWith` (string) - The string to replace instances of `replaceString` with. Again, %USERNAME% will be replaced with the username of the player.

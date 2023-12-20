_Last updated Dec. 19th 2023_

## Auction Macro Config

### minecraft
- `emails` (string) - The email associated with your Minecraft account. Your account credentials will be saved to ./cache/email/

### page
- `port` (number) - The port to run the webpage on.
- `enabled` (boolean) - Whether or not to run the webpage.
- `password` (string) - The password to access the webpage.

### webhook
- `webhook_url` (string) - The webhook url to send notifications to. Set to empty string to disable.

### bed_flips
- `spam_buy_delay` (number) - The delay between each buy request (in milliseconds)
- `pre_bed_spam` (number) - The amount of time to wait before spamming the bed button (in milliseconds)
- `skip_enabled` (boolean) - Whether or not to use "skip" mode. Skip mode will drastically improve buy times.

### actions
- `duration` (string) - The duration of the auction. (e.g. 6h, 12h, 24h, 48h)
- `claim_all` (boolean) - Whether or not to claim all items in the auction house, even if they are not yours.
- ~~`save_queue` (boolean) - Whether or not to save the buy and sell queue to a file. Broken as of now.~~
- `round_prices` (boolean) - Whether or not to round prices when listing the auction.
- `round_to` (number) - The number to round prices to. (e.g. 1000, 10000, 100000)

### flips
- `min_profit` (number) - The minimum profit for a flip to be bought. (e.g. 1000, 10000, 100000)
- `min_profit_percentage` (number) - The minimum profit percent for a flip to be bought. (e.g. 10, 20, 25)
- `sell_overflow_multiplier` (number) - The multiplier to the `sell_overflow_base` when entering overflow mode, where no more auction slots are available. (e.g. 1.1, 1.2, 1.25)
- `sell_overflow_base` (number) - Replaces `min_profit` when entering overflow mode, where no more auction slots are available. (e.g. 1000, 10000, 100000)
- `min_volume` (number) - The minimum sales/day for a flip to be bought. (e.g. 1, 2, 3)
- `sort_flips` (string) - The method to sort flips by. (e.g. descending, ascending, random)
- `disable_auto_relist` (list) - A collection of item ids to disable auto relist for. (e.g. ["HYPERION", "DARK_CLAYMORE"])
- ~~`disable_auto_relist_attributes` (list) - A collection of item attributes to disable auto relist for. (e.g. ["ultimate_chimera:1"]). Broken as of now.~~

### api
- `binmaster_key` (string) - The binmaster key to use for the flip-finding api.
- `hypixel_api_key` (string) - The hypixel api key. Obtained through developer.hypixel.net
- `manually_set_coop_count` (number) - The number of coop members to use when manually setting the coop count. (e.g. 1, 2, 3). Set to -1 to automatically detect coop count.

### logger
- `colorfulLog` (boolean) - Whether or not to use colorful logging.
- `logDate` (boolean) - Whether or not to log the date.
- `logChat` (boolean) - Whether or not to log chat messages.
- `prefix` (string) - The prefix for all messages for logging. %USERNAME% will be replaced with the username of the player.
- `replaceString` (string) - The string in the log that will be replaced by `replaceWith`. Again, %USERNAME% will be replaced with the username of the player.
- `replaceWith` (string) - The string to replace instances of `replaceString` with. Again, %USERNAME% will be replaced with the username of the player.
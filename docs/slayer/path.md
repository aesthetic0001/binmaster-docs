_Last updated Dec. 20th 2023_

## Slayer Path Docs

### Types of path instructions:

`match_mode`:
- **Description**: The island type where the path should start. It is the "mode" that you see after typing /locraw
- **Example**: `match_mode combat_1`

`mode_chat`:
- Description: The message that should be sent in order to get into the specified mode
- **Example**: `mode_chat /warp spider`

`execute_pre_path`:
- **Description**: Executes a command prior to running the path. Set it to 'none' for no command
- **Example**: `execute_pre_path /warp void`

`wait`:
- **Description**: Pauses execution for a specified amount of time (milliseconds)
- **Example**: `wait 1000`

`chat`:
- **Description**: Sends a general chat message
- **Example**: `chat Hello World!`

`goto`:
- **Description**: Moves to specified coordinates (x, y, z)
- **Example**: `goto 100 64 -200`

`equip`:
- **Description**: Swaps to a hotbar item by its skyblock ID
- **Example**: `equip SUPERBOOM_TNT`

`use_at`:
- **Description**: Uses an item at specified coordinates (x, y, z)
- **Example**: `use_at 102 65 -198`

`look`:
- **Description**: Changes the viewing direction to specified coordinates
- **Example**: `look 105 66 -201`

`etherwarp_to`:
- **Description**: Etherwarps to specified coordinates.
- **Example**: `etherwarp_to 150 75 -250`

`right_click`:
- **Description**: Right-clicks current held item
- **Example**: `right_click`

`controlstate`:
- **Description**: Changes the state of a control ('sneak', 'jump', 'sprint', 'forward', 'back', 'left', 'right') to 'on' or 'off'.
- **Example**: `controlstate jump on`

`assert_position`:
- **Description**: Checks if the current position is within a certain distance of the specified coordinates.
- **Example**: `assert_position 100 64 -200 5`

`look_at_for`:
- **Description**: Looks at a specific position for a set duration of time.
- **Example**: `look_at_for 108 67 -204 500`

`assertion_start`:
- **Description**: Defines the start of a series of actions with an assertion.
- **Example**:
```
assertion_start
...stuff to execute prior to the assertion. these instructions will be re-executed if the assertion fails...
assert_position x y z
...stuff that will happen after the assertion passes...
```

### How to write an initial path file:
Name your initial path file `{slayer}.path` and place it in the `paths` folder. For example, if you are writing a path for zombie slayer, you would name it `zombie.path`. The path file should be formatted like this:

At the very top of the path file, include `match_mode`, `mode_chat`, and `execute_pre_path`. These are required for any initial path file. For example, for hub zombie slayer, you would write:
```
match_mode hub
mode_chat /hub
execute_pre_path none
```

Then you can include any other instructions you want, specified above.

### How to write a farm path file:
Name your farm path file `{slayer}_farm.path` and place it in the `paths` folder. For example, if you are writing a farm path for zombie slayer, you would name it `zombie_farm.path`.

Unlike initial path files, farm path files should have various `goto` instructions for places you want the bot to go to when there are no more spawn mobs for your slayer. For example, for hub zombie slayer, you could write:
```
goto -146 57 -99
goto -96 48 -110
goto -46 56 -135
goto -99 39 -86
goto -127 42 -139
```
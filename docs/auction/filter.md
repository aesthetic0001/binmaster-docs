_Last updated Dec. 19 2023_

## What is a filter?
A filter is what is used in order for the flipper to determine whether or not to purchase an item

## Configurable options in the filter:
`blacklist`: a list of item IDs that you wish to not have the bot buy. IDs are viewable through the console (it shows `Filter allowed/denied: (item ID goes here)`
`whitelist`: a list of item IDs that you wish to be given the ability to bypass the `blacklist` option. They are structured in the format:
```json
"ITEM_ID=identifier": {
  "profit": the profit at which this triggers,
  "profit_percentage": the profit percentage at which this triggers
}
``` 
ie.
```json
"ATOMSPLIT_KATANA=global:true": {
  "profit": 20000000,
  "profit_percentage": 50
}
```
`user flip finder`: a set of manually defined rules for pricing certain items. It will append the value specified to the profit price and list price. Similar in format to whitelist.
```json
"ITEM_ID=identifier": {
  "scaleFactor": how much the profit should be multiplied by,
  "overwritePrice": a manual price for the item. set to 0 or false to disable this
}
``` 
ie.
```json
"ATOMSPLIT_KATANA=global:true": {
  "scaleFactor": 0.5,
  "overwritePrice": 0
}
```
will multiply the profit by 0.5, so if the atomsplit were at 50m profit, the user finder would modify that to only 25m.

and
```json
"ATOMSPLIT_KATANA=global:true": {
  "scaleFactor": 0.5,
  "overwritePrice": 100000000
}
```
will set all atomsplit prices to 100 million

### global:
Whitelist filter settings which apply to all flips

> Profit and profit percentage:
These are settings that will adjust the threshold at which any item (regardless of whether or not it is in whitelist) is allowed to bypass the filter

`profit`: the profit at which this triggers
`profit_percentage`: the profit percentage at which this triggers

> Flipper modes:
These are the various flipper pricing modes which are used. Toggle any that you do not wish to use by setting its value to false.

ie.
```json
"flipper_modes": {
      "attribute-direct-target": {
        "enabled": true,
        "min_volume": 1
      },
      "attribute-target": {
        "enabled": true,
        "min_volume": 1.5
      },
      "direct-target-pet": {
        "enabled": true,
        "min_volume": 1
      },
      "target-pet": {
        "enabled": true,
        "min_volume": 2
      },
      "direct-target": {
        "enabled": true,
        "min_volume": 1
      },
      "target": {
        "enabled": true,
        "min_volume": 1
      },
      "lbin": {
        "enabled": true,
        "min_volume": 1
      }
    }
```
will have all flipper modes enabled whereas
```json
"flipper_modes": {
      "attribute-direct-target": {
        "enabled": false,
        "min_volume": 1
      },
      "attribute-target": {
        "enabled": false,
        "min_volume": 1.5
      },
      "direct-target-pet": {
        "enabled": true,
        "min_volume": 1
      },
      "target-pet": {
        "enabled": true,
        "min_volume": 2
      },
      "direct-target": {
        "enabled": true,
        "min_volume": 1
      },
      "target": {
        "enabled": true,
        "min_volume": 1
      },
      "lbin": {
        "enabled": true,
        "min_volume": 1
      }
    }
```
will have all attribute flips disabled
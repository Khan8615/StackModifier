This plugin will seamlessly handle all of the ugly side effects and glitches. Thanks to StackModifier's feature additions, it makes it feel just like Rusts default behaviot, but better!

## Known Conflicts

* Magic Coin (uses some of the same hooks); set up config in it correctly to not conflict
* Custom Skin Stack Fix (not needed this handles it properly)
* Stack Size Controller (cannot have 2 of the same plugins basically)
* Extra Loot (causes a stacking bug when a reboot occurs)
* Compound Options 
  * If stack modifier loads after compound options, some compound options may not get set during the restart process
  * To fix, reload compound options

## Features

* Has a UI Editor
* Blocks Player movements while using UI Editor
* This plugin has 2 commands and no lang file
* Supports stacking of liquids
* Supports Stacking of Fuel Containers (hats, tools, etc.)
* Supports Stacking of Guns
* Supports Stacking of Skins
* Works with SkinBox plugins
* Supports Stacking of Custom Items
* Supports Stacking of Custom Items with Custom Display Names 
* Supports Stacking of Key Cards without losing the stack when swiping
* The largest possible value in C# is 2,147,483,647 Which means anything over this stacksize will break the plugin

![](https://i.imgur.com/ap7pdmf.png)

## Getting Started - Click Either Image to play videos

[ ![ Stack Modifier Tutorial ](https://i.imgur.com/5LWrCQG.jpg)](https://youtu.be/6aI5uH9xKsw)
[ ![ Stack Modifier Beta ](https://img.youtube.com/vi/6gXnJvX4BJc/0.jpg)](https://www.youtube.com/watch?v=6gXnJvX4BJc)

## Permissions

* `stackmodifier.bypass` -- Allows players to ignore the blocked stackable items list.
* `stackmodifier.admin` -- Allows players use the UI Editor.

## Chat Commands

* `/stackmodifier` -- Opens Editor UI, Must enable config option  "Enable UI Editor": true ) Requires [ImageLibrary](https://umod.org/plugins/image-library)
* `/resetvenders` -- Requires being an admin ( only resets facepunches messedup vendors, not all )
* `/stackmodifiercolor <inputpanel|inputtext|text|transparent> <color> <alpha|ex, 0.98>`
  Example `/stackmodifiercolor inputpanel #207086 0.25`

## UI Editor Commands

* `set 8` -- Inside a categories Filter Bar, type set and a value and it will apply it to the whole category,
* `reset` -- Inside a categories Filter Bar type reset hit the enter key or click out of the field and it resets it.
* ( if you reset or set, re-click the Category Tab to refresh it before making more changes )
* ( otherwise you will have to do your first edit twice for it to start working again ) 

* Please note the UI Editor is new, and there are some things to work out still with it. 

## UI Editor Without ImageLibrary?
* At the top of the config you will see the following setting set to true save and reload.
* "Disable ImageLibrary Requirement / Images for UI Editor": false,  < Disables images and allows full use
![](https://i.imgur.com/UAQnFJL.png)

## Having Problems?

* Warning this plugin is not compatibly with custom-skins-stacks-fix plugin since this already handles everything.
* If you already have a plugin that modify's the rust stacksizes you will first need to remove that plugin.
* Then you simply load StackModifier onto your server open the config and start editing the Modified values to your new stacksize amounts! 
* When you are done simply save and reload the plugin! `oxide.reload StackModifier`

## How to revert to vanillia?

* Unload StackModifier, delete the config, and restart your server. 
* It will reset the config back to vanillia settings allowing you to start over if you went and did the Quick/Dirty method for switching plugins. 

## Configuration

```json
{
  "Enable UI Editor": true,
  "Disable ImageLibrary Requirement / Images for UI Editor": false,
  "Sets editor color command": "stackmodifiercolor",
  "Sets Reset Vendors command": "resetvenders",
  "Sets Default Category to open": "Attire",
  "Stack Modifier UI Title": "Stack Modifier Editor ◝(⁰▿⁰)◜",
  "UI - Stack Size Label": "Stack Size",
  "UI - Set Stack Label": "Set Stack",
  "UI - Search Bar Label": "Filter ▶",
  "UI - Back Button Text": "◀",
  "UI - Forward Button Text": "▶",
  "UI - Close Label": "✖",
  "UI - Background Image Url": "https://i.imgur.com/Jej3cwR.png",
  "Sets any item to this image if image library does not have one for it.": "https://imgur.com/BPM9UR4.png",
  "Colors": {
    "InputPanel": {
      "Hex": "#0E0E10",
      "Rgb": "0.0549019607843137 0.0549019607843137 0.0627450980392157 0.98"
    },
    "InputText": {
      "Hex": "#FFE24B",
      "Rgb": "1 0.886274509803922 0.294117647058824 0.15"
    },
    "TextColor": {
      "Hex": "#FFFFFF",
      "Rgb": "1 1 1 1"
    },
    "Transparency": {
      "Hex": "#",
      "Rgb": "0 0 0 0.95"
    }
  },
  "Revert to Vanilla Stacks on unload (Recommended true if removing plugin)": false,
  "Disable Ammo/Fuel duplication fix (Recommended false)": false,
  "Enable VendingMachine Ammo Fix (Recommended)": true,
  "Blocked Stackable Items": [
    "shortname"
  ],
  "Category Stack Multipliers": {
    "Attire": 1,
    "Misc": 1,
    "Items": 1,
    "Ammunition": 1,
    "Construction": 1,
    "Component": 1,
    "Traps": 1,
    "Electrical": 1,
    "Fun": 1,
    "Food": 1,
    "Resources": 1,
    "Tool": 1,
    "Weapon": 1,
    "Medical": 1
  },
  "Stack Categories": {
    "Attire": {
      "hat.wolf": {
        "DisplayName": "Wolf Headdress",
        "Modified": 10
      },
      "horse.shoes.basic": {
        "DisplayName": "Basic Horse Shoes",
        "Modified": 10
      }
    },
    "Misc": {
      "fogmachine": {
        "DisplayName": "Fogger-3000",
        "Modified": 10
      },
      "sickle": {
        "DisplayName": "Sickle",
        "Modified": 10
      }
    },
    "Items": {
      "kayak": {
        "DisplayName": "Kayak",
        "Modified": 10
      },
      "map": {
        "DisplayName": "Paper Map",
        "Modified": 10
      }
    },
    "Ammunition": {
      "ammo.grenadelauncher.buckshot": {
        "DisplayName": "40mm Shotgun Round",
        "Modified": 20
      },
      "ammo.rocket.sam": {
        "DisplayName": "SAM Ammo",
        "Modified": 10
      }
    },
    "Construction": {
      "door.double.hinged.metal": {
        "DisplayName": "Sheet Metal Double Door",
        "Modified": 10
      },
      "building.planner": {
        "DisplayName": "Building Plan",
        "Modified": 10
      }
    },
    "Component": {
      "bleach": {
        "DisplayName": "Bleach",
        "Modified": 2
      },
      "vehicle.module": {
        "DisplayName": "Generic vehicle module",
        "Modified": 10
      }
    },
    "Traps": {
      "trap.bear": {
        "DisplayName": "Snap Trap",
        "Modified": 30
      },
      "samsite": {
        "DisplayName": "SAM Site",
        "Modified": 10
      }
    },
    "Electrical": {
      "ceilinglight": {
        "DisplayName": "Ceiling Light",
        "Modified": 10
      },
      "wiretool": {
        "DisplayName": "Wire Tool",
        "Modified": 100
      }
    },
    "Fun": {
      "firework.boomer.blue": {
        "DisplayName": "Blue Boomer",
        "Modified": 200
      },
      "telephone": {
        "DisplayName": "Telephone",
        "Modified": 10
      }
    },
    "Food": {
      "apple": {
        "DisplayName": "Apple",
        "Modified": 100
      },
      "woodtea.pure": {
        "DisplayName": "Pure Wood Tea",
        "Modified": 100
      }
    },
    "Resources": {
      "skull.human": {
        "DisplayName": "Human Skull",
        "Modified": 10
      },
      "wood": {
        "DisplayName": "Wood",
        "Modified": 10
      }
    },
    "Tool": {
      "tool.instant_camera": {
        "DisplayName": "Instant Camera",
        "Modified": 10
      },
      "bucket.water": {
        "DisplayName": "Water Bucket",
        "Modified": 10
      }
    },
    "Weapon": {
      "gun.water": {
        "DisplayName": "Water Gun",
        "Modified": 10
      },
      "spear.wooden": {
        "DisplayName": "Wooden Spear",
        "Modified": 10
      }
    },
    "Medical": {
      "blood": {
        "DisplayName": "Blood",
        "Modified": 100
      },
      "bandage": {
        "DisplayName": "Bandage",
        "Modified": 30
      }
    }
  }
}
```

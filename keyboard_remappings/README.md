# Keyboard Remappings

In this section, we will install and configure free software to remap keys, create complex shortcuts, and change keyboard behavior.

## Step 1: Install

Install [Karabiner-Elements](https://karabiner-elements.pqrs.org) on your machine.

The software needs input monitoring permissions to capture and modify keystrokes. You will need to make multiple changes to your systems settings. Follow the directions while installing the software.

## Step 2: About the Meta Key

The "meta key" is the key that you hold down which changes the meaning of all other keys.

The [caps lock] key is large and accessible but useless to most users. We will configure our keyboard so that when the caps lock key is held, other keys have a different meaning. For instance, [caps lock] + [L] could launch your Linux terminal or make it the top window.

The most valuable key are the right home keys ([J], [K], [L], [;]) shown in red in the image below. The next most valuable are those shown in orange.

![meta key illustration](images/keyboard.jpg)


#### Define Your Meta Key

1. Open the Karabiner-Elements settings.
1. In left sidebar, choose "Complex Modifications"
1. Click on "Add your own rule"
1. Copy and paste the contents below and choose "Save"

![meta key definition](images/meta_key_definition.png)


```json
{
    "manipulators": [
        {
            "description": "Change caps_lock to command+control+option+shift.",
            "from": {
                "key_code": "caps_lock",
                "modifiers": { "optional": ["any"] }
            },
            "parameters": {
                "basic.to_if_alone_timeout_milliseconds": 150,
                "basic.to_if_held_down_threshold_milliseconds": 150
            },
            "to_if_alone": [{ "key_code": "escape" }],
            "to_if_held_down": [
                {
                    "key_code": "left_shift",
                    "modifiers": ["left_command", "left_control", "left_option"]
                }
            ],
            "type": "basic"
        }
    ]
}
```

Next, make you first remapping which will allow you to cycles tabs with [caps lock] + [N]:

1. In left sidebar, choose "Complex Modifications"
1. Click on "Add your own rule"
1. Copy and paste the contents below and choose "Save"

```json
{
    "description": "Hyper + N -> next tab",
    "manipulators": [
        {
            "from": {
                "key_code": "n",
                "modifiers": { "mandatory": ["command", "shift", "option", "control"] }
            },
            "to_if_alone": [
                {
                    "key_code": "tab",
                    "modifiers": ["control"]
                }
            ],
            "type": "basic"
        }
    ]
}
```


## Additional Meta Keys (Advanced)

It's nice to have the letter of the second key have some meaning (like [N] for next tab, or [L] for Linux termina). Holding the [caps lock] meta key ties up your left hand leaving only a few letters for the second key (to be pressed with your right hand).

You can configure Karabiner-Elements to use [caps lock] plus a second key as the hyper to create more freedom. For instance, for operations concerning moving and resizing windows, one might use [caps lock] + [W] + (any third key). A specific example would be [caps lock] + [W] + [J] maximizes the current window.

One could also use left tab or left shift as a different meta key.

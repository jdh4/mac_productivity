# Raycast

[Raycast](https://www.raycast.com) is a collection of productivity tools within an extendable launcher. See the [Raycast Mac Manual](https://manual.raycast.com/mac).

## Install

Install [Raycast](https://www.raycast.com)  on your Mac.

## Configuration

[Set the global hotkey](https://manual.raycast.com/hotkey) to launch Raycast and turn off Spotlight.

Launch Raycast with `[command] + [space]` then do `[command] + [comma]`.

![General Settings](images/raycast_general_settings.png)

## Snippets

A [snippet](https://manual.raycast.com/snippets) is a block of text that can be recalled. Snippets are handy for frequently used text such as canned email responses, code or emojis.

To create a snippet:

1. Launch Raycast
1. Search "Create snippet"
1. Create a snippet by giving it a name and entering the snippet

Use keywords to be replaced by a specified snippet.

Use dynamic placeholders {}  <kbd>Control</kbd> + <kbd>Option</kbd> + <kbd>Shift</kbd> + <kbd>Q</kbd> is **⌃⌥⇧⌘Q**

Learn about using [dynamic placeholders](https://manual.raycast.com/dynamic-placeholders) in snippets.

Using the snippet below, after copying the person's first name to the clipboard, `{clipboard}` will be replaced:

```
Hi {clipboard},

Yes, I will attend. See you there.

Jon
```

Here is a code example that using `{cursor}` and `{date}` -- it computes the number of CPU-hours used in the last week for user `jdh4`:

```
sacct -M della -u jdh4{cursor} -X -n -S {date format="yyyy-MM-dd" offset="-7d"}T00:00:00 -E now -o cputimeraw | awk '{sum += $1} END {print int(sum/3600)}'
```

**Exercise**: Create two or three snippets.

Note that rather than typing the keyword, one could use Karabiner-Elements to assign it to a key. For instance, if the keyword of the snippet is `@attend`:

```json
{
    "description": "f6 to attend snippet",
    "manipulators": [
        {
            "from": { "key_code": "f6" },
            "to": [
                {
                    "key_code": "2",
                    "modifiers": ["shift"]
                },
                { "key_code": "a" },
                { "key_code": "t" },
                { "key_code": "t" },
                { "key_code": "e" },
                { "key_code": "n" },
                { "key_code": "d" }
            ],
            "type": "basic"
        }
    ]
}
```

## Quicklinks

Learn about and create a few [Quicklinks](https://manual.raycast.com/quicklinks).

**Exercise 1**: Add the "Search Wikipedia" Quicklink. Then select a word in an app and run the Wikipedia Quicklink.

**Exercise 2**: Create a new quicklink that opens your favorite browser to `https://www.princeton.edu/` or another URL. Consider making a `Hotkey` so that you can get there using only the keyboard.

## Calculator

To use the calculator just enter the calculations:

![Calculator](images/raycast_calculator.png)

The calculator history is stored.

## Window Management

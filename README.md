# Vaunt UI Library

A clean, modern Roblox exploit UI library with themes, config system, and full element support.

---

## Setup

```lua
local Vaunt = loadstring(game:HttpGet("YOUR_RAW_URL"))()

local Win = Vaunt:Window({
    Title  = "Hub Name",
    Icon   = "crown",
    Footer = "v1.0",
    Key    = Enum.KeyCode.RightControl,
})
```

---

## Structure

```lua
Win:Separator("Section Label")

local Tab  = Win:Tab("Tab Name", "icon")
local Page = Tab:Page("Page Name", "icon")
local Sec  = Page:Section("Section Name", "Left")  -- "Left" or "Right"
```

---

## Elements (Inside a Section)

### Toggle
```lua
Sec:Toggle("Feature Name", "featureFlag", false, "Description", function(state)
    print(state)
end)
```

### Checkbox
```lua
Sec:Checkbox("Option Name", "optionFlag", false, "Description", function(state)
    print(state)
end)
```

### Slider
```lua
Sec:Slider("Value Name", "valueFlag", 0, 100, 50, "Description", function(val)
    print(val)
end)
```

### Keybind
```lua
Sec:Keybind("Bind Name", "bindFlag", Enum.KeyCode.F, "Description", function(key)
    print(key)
end)
```

### Button
```lua
Sec:Button("Button Name", "Description", function()
    -- action
end)
```

### TextBox
```lua
Sec:TextBox("Input Name", "inputFlag", "default text", "Description", function(text)
    print(text)
end)
```

### Dropdown
```lua
Sec:Dropdown("List Name", "listFlag", {"Option A", "Option B", "Option C"}, "Description", function(val)
    print(val)
end)
```

### Multi-Dropdown
```lua
Sec:MultiDD("Multi Name", "multiFlag", {"Option A", "Option B", "Option C"}, "Description", function(tbl)
    for k, v in pairs(tbl) do print(k, v) end
end)
```

### Color Picker
```lua
Sec:ColorPicker("Color Name", "colorFlag", Color3.fromRGB(255, 255, 255), 1, "Description", function(color, alpha)
    print(color, alpha)
end)
```

### Label
```lua
Sec:Label("Some text to display")
```

### Paragraph
```lua
Sec:Paragraph("Title", "Body text goes here.")
```

---

## Elements (Directly on a Page)

When adding elements directly to a page without a section, pass the side `"Left"` or `"Right"` before the callback.

```lua
Page:Toggle("Feature Name", "featureFlag", false, "Description", "Left", function(state) end)
Page:Checkbox("Option Name", "optionFlag", false, "Description", "Right", function(state) end)
Page:Slider("Value Name", "valueFlag", 0, 100, 50, "Left", function(val) end, "Description")
Page:Keybind("Bind Name", "bindFlag", Enum.KeyCode.F, "Left", function(key) end, "Description")
Page:Button("Button Name", "Description", "Right", function() end)
Page:TextBox("Input Name", "inputFlag", "default", "Left", function(text) end, "Description")
Page:Dropdown("List Name", "listFlag", {"A", "B", "C"}, "Left", function(val) end, "Description")
Page:MultiDD("Multi Name", "multiFlag", {"A", "B", "C"}, "Right", function(tbl) end, "Description")
Page:ColorPicker("Color Name", "colorFlag", Color3.new(1,1,1), 1, "Left", function(col, alpha) end, "Description")
Page:Label("Some text", "Left")
Page:Paragraph("Title", "Body text.", "Right")
```

---

## Notification

```lua
Vaunt:Notify("Title", "Message here.", 4)
```

---

## Config System

Adds a built-in **Settings** tab with config save/load/delete and theme switching.

```lua
Vaunt:ConfigSystem(Win)
```

---

## Reading Flags

```lua
print(Vaunt.Flags["featureFlag"])
print(Vaunt.Flags["valueFlag"])
print(Vaunt.Flags["listFlag"])
print(Vaunt.Flags["colorFlag"].Color)
print(Vaunt.Flags["colorFlag"].Transparency)
```

---

## Setting Elements Programmatically

```lua
Vaunt.Elements["featureFlag"].Set(true)
Vaunt.Elements["valueFlag"].Set(75)
Vaunt.Elements["listFlag"].Set("Option B")
Vaunt.Elements["multiFlag"].Set({ ["Option A"] = true, ["Option B"] = true })
Vaunt.Elements["colorFlag"].Set({ Color = Color3.fromRGB(0, 255, 128), Transparency = 1 })
```

---

## Available Themes

| Name | Description |
|:-----|:------------|
| Vaunt (Default) | Deep purple |
| Crimson | Red tones |
| Ocean | Blue tones |
| Toxic | Green tones |
| Cyberpunk | Neon pink & cyan |
| Midnight | Soft blue |
| Ember | Orange & fire |
| Arctic | Ice blue |
| Royal | Rich purple |
| Mono | Black & white |
| Rose Gold | Pink & gold |
| Deep Space | Dark navy blue |

---

## Available Icons

Vaunt uses [Lucide](https://lucide.dev) icon names. Some commonly used ones:

`sword` `swords` `shield` `skull` `target` `crosshair` `eye` `eye-off` `crown` `star` `zap` `flame` `ghost` `activity` `user` `users` `settings` `folder` `save` `trash` `search` `refresh` `home` `lock` `unlock` `key` `code` `terminal` `tool` `wrench` `cpu` `wifi` `monitor` `layers` `camera` `heart` `trophy` `gamepad` `moon` `sun` `music` `volume` `map` `globe` `flag` `bell` `send` `link` `list` `grid` `tag` `message` `clock` `filter` `download` `upload` `edit` `pen` `box` `share` `power` `arrow-up` `arrow-down` `arrow-left` `arrow-right` `move` `play` `pause` `trending-up` `percent`

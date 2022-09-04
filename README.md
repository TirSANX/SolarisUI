# Solaris Library
This documentation is for the stable release of Solaris Library.

## Booting the Library
```lua
local SolarisLib = loadstring(game:HttpGet("https://raw.githubusercontent.com/TrapstarKSSKSKSKKS/Main/main/SolarisLib.lua"))()
```



## Creating a Window
```lua
local win = SolarisLib:New({
  Name = "SolarisLib",
  FolderToSave = "SolarisLibStuff"
})

--[[
  Name - Title of the UI <string>
  FolderToSave - Name of the folder where the UI files will be stored <string>
]]
```



## Creating a Tab
```lua
local Tab = win:Tab("Tab 1")

-- win:Tab(title <string>)
```

## Creating a Section
```lua
local sec = tab:Section("Section")

-- tab:Section(title <string>)
```
Elements must be added to sections.

## Notifying the user
```lua

SolarisLib:Notification("Test", "This is a notification test.")

-- SolarisLib:Notification("title <String>", "description <string>")

```



## Creating a Button
```lua

sec:Button("Button", function()
  print("Hello")
end)

-- sec:Button(title <string>, callback <function>)

```


## Creating a Checkbox toggle
```lua

local toggle = sec:Toggle("Toggle", false,"Toggle", function(t)
  print(t)
end)

-- sec:Toggle(title <string>,default <boolean>, flag <string>, callback <function>)

```

### Changing the value of an existing Toggle
```lua

toggle:Set(true)

-- toggle:Set(state <boolean>)

```



## Creating a Color Picker
```lua

sec:Colorpicker("Colorpicker", Color3.fromRGB(255,255,255),"Colorpicker", function(t)
  print(t)
end)

-- sec:Colorpicker(title <string>, default <color3>, flag <string>, callback <function>)

```

## Creating a Slider
```lua

local slider = sec:Slider("Slider", 0,25,0,2.5,"Slider", function(t)
  print(t)
end)

-- sec:Slider(title <string>,minimum <number>,max <number>,default <number>,increment <number>, flag <string>, callback <function>)

```

### Change Slider Value
```lua

slider:Set(10)

-- slider:Set(state <number>)

```
Make sure you make your slider a variable (local slider = sec:Slider...) for this to work.


## Creating a Label
```lua

local label = sec:Label("Label")

-- sec:Label(text <string>)

```

### Changing the value of an existing label
```lua

label:Set("NewLabel!")

-- label:Set(text <string>)

```


## Creating an Adaptive Input
```lua

sec:Textbox("Textbox", true, function(t)
  print(t)
end)

-- sec:Textbox(title <string> ,disappear <boolean>, callback <function>)

```


## Creating a Keybind
```lua

sec:Bind("Normal Bind", Enum.KeyCode.F, false, "BindNormal", function()
  print("Bind pressed")
end)

-- sec:Bind(title <string>, default <keycode>, hold <boolean>, flag <string>, callback <function>)

```

## Creating a Hold Keybind
```lua

sec:Bind("Hold Bind", Enum.KeyCode.E, true, "BindHold", function(t)
   print(t)
end)

-- sec:Bind(title <string>, default <keycode>, hold <boolean>, flag <string>, callback <function>)

```

### Chaning the value of a bind
```lua

bind:Set(Enum.KeyCode.X)

-- bind:Set(state <keycode>)

```


## Creating a Dropdown
```lua

local dropdown = sec:Dropdown("Dropdown", {"1","2","3"},"","Dropdown", function(t)
  print(t)
end)

-- sec:Dropdown(title <string>,options <table>,default <string>, flag <string>, callback <function>)

```

## Creating a Multi Dropdown
```lua

local multidropdown = sec:MultiDropdown("Multi Dropdown", {"1", "2", "3", "4"},{"3", "4"},"Dropdown", function(t)
  print(table.concat(t, ", "))
end)

-- sec:MultiDropdown(title <string>,options <table>,default <table>, flag <string>, callback <function>)

```


### Adding a set of new Dropdown buttons to an existing menu
```lua

Dropdown:Refresh(List <table>,true <boolean>)

```

The above boolean value "true" is whether or not the current buttons will be deleted.

### Selecting a dropdown option
```lua

Dropdown:Set("dropdown option")

-- Dropdown:Set(option <table>)

```


### Making your interface work with configs.

The `Flag = <string>` argument is the ID of an element in the config file.
Config files are made for every game the library is launched in.
Flags only work with the toggle, slider, dropdown, bind, and colorpicker.

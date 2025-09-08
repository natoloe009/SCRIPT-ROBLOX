# Orion Library
This documentation is for the Modified Orion Library.

## Booting the Library
```lua
local OrionLib = loadstring(game:HttpGet(('[https://raw.githubusercontent.com/natoloe009/TEST-ANYTHING-/refs/heads/main/orio%20ui.txt](https://raw.githubusercontent.com/natoloe009/0079igo97rgiiyr7ub/refs/heads/main/ORION_KAGA_MODIFY.txt)'),true))()
```



## Creating a Window
```lua
local Window = OrionLib:MakeWindow({
    Name = "Title of the library", 
    HidePremium = false, 
    SaveConfig = true, 
    IntroEnabled = false, 
    ConfigFolder = "YourConfig",
    IntroText = "Intro Text",
    IntroIcon = "rbxassetid://",
    Icon = "rbxassetid://",
    CloseCallback = function() end
})

--[[
Name = <string> - The name of the UI.
HidePremium = <bool> - Whether or not the user details shows Premium status or not.
SaveConfig = <bool> - Toggles the config saving in the UI.
ConfigFolder = <string> - The name of the folder where the configs are saved.
IntroEnabled = <bool> - Whether or not to show the intro animation.
IntroText = <string> - Text to show in the intro animation.
IntroIcon = <string> - URL to the image you want to use in the intro animation.
Icon = <string> - URL to the image you want displayed on the window.
CloseCallback = <function> - Function to execute when the window is closed.
]]
```



## Creating a Tab
```lua
local Tab = Window:MakeTab({
    Name = "Tab 1",
    Icon = "rbxassetid://4483345998",
    PremiumOnly = false
})

--[[
Name = <string> - The name of the tab.
Icon = <string> - The icon of the tab.
PremiumOnly = <bool> - Makes the tab accessible to Sirius Premium users only.
]]
```
## Creating a Section
```lua
local Section = Tab:AddSection({
    Name = "Section"
})

--[[
Name = <string> - The name of the section.
]]
```
You can add elements to sections the same way you would add them to a tab normally.

## Notifying the user
```lua
OrionLib:MakeNotification({
    Name = "Title!",
    Content = "Notification content... what will it say??",
    Image = "rbxassetid://4483345998",
    Time = 5
})

--[[
Name = <string> - The title of the notification.
Content = <string> - The content of the notification.
Image = <string> - The icon of the notification.
Time = <number> - The duration of the notification.
]]
```



## Creating a Button
```lua
local Button = Tab:AddButton({
    Name = "Button!",
    Callback = function()
        print("button pressed")
    end    
})

--[[
Name = <string> - The name of the button.
Callback = <function> - The function of the button.
]]
```

```lua
Button:Set("New Button Text")
```


## Creating a Checkbox toggle
```lua
local Toggle = Tab:AddToggle({
    Name = "This is a toggle!",
    Default = false,
    Callback = function(Value)
        print(Value)
    end,
    Color = Color3.fromRGB(9, 99, 195), -- Optional
    Flag = "toggle_flag", -- Optional
    Save = true -- Optional
})

--[[
Name = <string> - The name of the toggle.
Default = <bool> - The default value of the toggle.
Callback = <function> - The function of the toggle.
Color = <Color3> - The color of the toggle when enabled.
Flag = <string> - The flag identifier for config saving.
Save = <bool> - Whether to save this toggle's value in config.
]]
```

### Changing the value of an existing Toggle
```lua
Toggle:Set(true)
```

## Creating a Slider
```lua
local Slider = Tab:AddSlider({
    Name = "Slider",
    Min = 0,
    Max = 20,
    Default = 5,
    Color = Color3.fromRGB(255, 255, 255),
    Increment = 1,
    ValueName = "bananas",
    Callback = function(Value)
        print(Value)
    end,
    Flag = "slider_flag", -- Optional
    Save = true -- Optional
})

--[[
Name = <string> - The name of the slider.
Min = <number> - The minimal value of the slider.
Max = <number> - The maxium value of the slider.
Increment = <number> - How much the slider will change value when dragging.
Default = <number> - The default value of the slider.
Color = <Color3> - The color of the slider.
ValueName = <string> - The text after the value number.
Callback = <function> - The function of the slider.
Flag = <string> - The flag identifier for config saving.
Save = <bool> - Whether to save this slider's value in config.
]]
```

### Change Slider Value
```lua
Slider:Set(2)
```
Make sure you make your slider a variable (local CoolSlider = Tab:AddSlider...) for this to work.


## Creating a Label
```lua
local Label = Tab:AddLabel("Label")

--[[
Text = <string> - The text content of the label.
]]
```

### Changing the value of an existing label
```lua
Label:Set("Label New!")
```


## Creating a Paragraph
```lua
local Paragraph = Tab:AddParagraph("Paragraph Title", "Paragraph Content")

--[[
Title = <string> - The title of the paragraph.
Content = <string> - The content of the paragraph.
]]
```

### Changing an existing paragraph
```lua
Paragraph:Set("New Title", "New Content")
```


## Creating an Adaptive Input
```lua
Tab:AddTextbox({
    Name = "Textbox",
    Default = "default box input",
    TextDisappear = true,
    Callback = function(Value)
        print(Value)
    end
})

--[[
Name = <string> - The name of the textbox.
Default = <string> - The default value of the textbox.
TextDisappear = <bool> - Makes the text disappear in the textbox after losing focus.
Callback = <function> - The function of the textbox.
]]
```


## Creating a Keybind
```lua
local Bind = Tab:AddBind({
    Name = "Bind",
    Default = Enum.KeyCode.E,
    Hold = false,
    Callback = function()
        print("press")
    end,
    Flag = "bind_flag", -- Optional
    Save = true -- Optional
})

--[[
Name = <string> - The name of the bind.
Default = <Enum.KeyCode> - The default value of the bind.
Hold = <bool> - Makes the bind work like: Holding the key > The bind returns true, Not holding the key > Bind returns false.
Callback = <function> - The function of the bind.
Flag = <string> - The flag identifier for config saving.
Save = <bool> - Whether to save this bind's value in config.
]]
```

### Chaning the value of a bind
```lua
Bind:Set(Enum.KeyCode.E)
```


## Creating a Dropdown menu
```lua
local Dropdown = Tab:AddDropdown({
    Name = "Dropdown",
    Default = "1",
    Options = {"1", "2"},
    Callback = function(Value)
        print(Value)
    end,
    Flag = "dropdown_flag", -- Optional
    Save = true -- Optional
})

--[[
Name = <string> - The name of the dropdown.
Default = <string> - The default value of the dropdown.
Options = <table> - The options in the dropdown.
Callback = <function> - The function of the dropdown.
Flag = <string> - The flag identifier for config saving.
Save = <bool> - Whether to save this dropdown's value in config.
]]
```

### Adding a set of new Dropdown buttons to an existing menu
```lua
Dropdown:Refresh({"Option1", "Option2"}, true)
```

The above boolean value "true" is whether or not the current buttons will be deleted.
### Selecting a dropdown option
```lua
Dropdown:Set("dropdown option")
```

# Multiple DropDown
```lua
local MultiDropdown = Tab:AddMultiDropdown({
    Name = "Multi Dropdown",
    Default = {"Option1"},
    Options = {"Option1", "Option2", "Option3"},
    Callback = function(Value)
        print(table.concat(Value, ", "))
    end,
    Flag = "multidropdown_flag", -- Optional
    Save = true -- Optional
})

--[[
Name = <string> - The name of the multi dropdown.
Default = <table> - The default selected values.
Options = <table> - The available options in the dropdown.
Callback = <function> - The function called when selection changes.
Flag = <string> - The flag identifier for config saving.
Save = <bool> - Whether to save this multi dropdown's value in config.
]]
```

```lua
local currentValues = MultiDropdown:GetValue()
```

```lua
MultiDropdown:Set({"Option1", "Option3"})
```

```lua
MultiDropdown:Clear()
```

### Select Theme 
```lua
-- Available themes: Default, Purple, Blue, DarkRed, CyberGreen, Gold
OrionLib.SelectedTheme = "Blue" -- Change the theme

-- Apply the theme change
OrionLib:SetTheme()
```

### Configuration
```lua
-- Save configuration manually
OrionLib:SaveCfg("ConfigName")

-- Load configuration manually
OrionLib:LoadCfg("ConfigContent")
```


### Destroy Orion
```lua
OrionLib:Destroy()
```


# Orion Library
This documentation is for the Modified Orion Library.

## Booting the Library
```lua
local OrionLib = loadstring(game:HttpGet(('https://raw.githubusercontent.com/natoloe009/TEST-ANYTHING-/refs/heads/main/orio%20ui.txt'),true))()
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

### Example 

```lua
local OrionLib = loadstring(game:HttpGet(('https://raw.githubusercontent.com/natoloe009/TEST-ANYTHING-/refs/heads/main/orio%20ui.txt'),true))()
-- Create window
local Window = OrionLib:MakeWindow({
    Name = "KaGa HUB - Premium Script",
    HidePremium = false,
    SaveConfig = true,
    ConfigFolder = "KaGaHUBConfigs",
    IntroEnabled = true,
    IntroText = "KaGa HUB",
    IntroIcon = "rbxassetid://8834748103",
    Icon = "rbxassetid://8834748103"
})

-- Create tabs
local MainTab = Window:MakeTab({
    Name = "Main",
    Icon = "rbxassetid://4483345998",
    PremiumOnly = false
})

local PlayerTab = Window:MakeTab({
    Name = "Player",
    Icon = "rbxassetid://4483345998",
    PremiumOnly = false
})

local VisualsTab = Window:MakeTab({
    Name = "Visuals",
    Icon = "rbxassetid://4483345998",
    PremiumOnly = false
})

local SettingsTab = Window:MakeTab({
    Name = "Settings",
    Icon = "rbxassetid://4483345998",
    PremiumOnly = false
})

-- Main Tab Content
local MainSection = MainTab:AddSection({
    Name = "Auto Farm"
})

local AutoFarmToggle = MainTab:AddToggle({
    Name = "Auto Farm",
    Default = false,
    Save = true,
    Flag = "AutoFarm",
    Callback = function(Value)
        if Value then
            OrionLib:MakeNotification({
                Name = "Auto Farm",
                Content = "Auto Farm enabled!",
                Image = "rbxassetid://4483345998",
                Time = 3
            })
            -- Start auto farm logic here
        else
            OrionLib:MakeNotification({
                Name = "Auto Farm",
                Content = "Auto Farm disabled!",
                Image = "rbxassetid://4483345998",
                Time = 3
            })
            -- Stop auto farm logic here
        end
    end
})

local FarmSpeedSlider = MainTab:AddSlider({
    Name = "Farm Speed",
    Min = 1,
    Max = 10,
    Default = 5,
    Color = Color3.fromRGB(255, 255, 255),
    Increment = 1,
    ValueName = "speed",
    Save = true,
    Flag = "FarmSpeed",
    Callback = function(Value)
        -- Update farm speed logic here
    end
})

local AutoSellToggle = MainTab:AddToggle({
    Name = "Auto Sell",
    Default = false,
    Save = true,
    Flag = "AutoSell",
    Callback = function(Value)
        -- Auto sell logic here
    end
})

local MainSection2 = MainTab:AddSection({
    Name = "Teleports"
})

local TeleportDropdown = MainTab:AddDropdown({
    Name = "Teleport Locations",
    Default = "Spawn",
    Options = {"Spawn", "Forest", "Desert", "Snow Area", "Volcano"},
    Save = true,
    Flag = "TeleportLocation",
    Callback = function(Value)
        OrionLib:MakeNotification({
            Name = "Teleporting",
            Content = "Teleporting to: " .. Value,
            Image = "rbxassetid://4483345998",
            Time = 3
        })
        -- Teleport logic here
    end
})

local TeleportButton = MainTab:AddButton({
    Name = "Teleport Now",
    Callback = function()
        local location = OrionLib.Flags["TeleportLocation"].Value
        OrionLib:MakeNotification({
            Name = "Teleporting",
            Content = "Teleporting to: " .. location,
            Image = "rbxassetid://4483345998",
            Time = 3
        })
        -- Execute teleport here
    end
})

-- Player Tab Content
local PlayerSection = PlayerTab:AddSection({
    Name = "Movement"
})

local SpeedToggle = PlayerTab:AddToggle({
    Name = "Speed Hack",
    Default = false,
    Save = true,
    Flag = "SpeedHack",
    Callback = function(Value)
        -- Speed hack logic here
    end
})

local SpeedSlider = PlayerTab:AddSlider({
    Name = "Speed Value",
    Min = 16,
    Max = 100,
    Default = 25,
    Color = Color3.fromRGB(255, 255, 255),
    Increment = 1,
    ValueName = "studs",
    Save = true,
    Flag = "SpeedValue",
    Callback = function(Value)
        -- Update speed value logic here
    end
})

local JumpToggle = PlayerTab:AddToggle({
    Name = "Jump Hack",
    Default = false,
    Save = true,
    Flag = "JumpHack",
    Callback = function(Value)
        -- Jump hack logic here
    end
})

local JumpPowerSlider = PlayerTab:AddSlider({
    Name = "Jump Power",
    Min = 50,
    Max = 200,
    Default = 50,
    Color = Color3.fromRGB(255, 255, 255),
    Increment = 5,
    ValueName = "power",
    Save = true,
    Flag = "JumpPower",
    Callback = function(Value)
        -- Update jump power logic here
    end
})

-- Visuals Tab Content
local VisualsSection = VisualsTab:AddSection({
    Name = "ESP"
})

local PlayerESPToggle = VisualsTab:AddToggle({
    Name = "Player ESP",
    Default = false,
    Save = true,
    Flag = "PlayerESP",
    Callback = function(Value)
        -- Player ESP logic here
    end
})


local ItemESPToggle = VisualsTab:AddToggle({
    Name = "Item ESP",
    Default = false,
    Save = true,
    Flag = "ItemESP",
    Callback = function(Value)
        -- Item ESP logic here
    end
})

local XRayToggle = VisualsTab:AddToggle({
    Name = "X-Ray Vision",
    Default = false,
    Save = true,
    Flag = "XRay",
    Callback = function(Value)
        -- X-Ray logic here
    end
})

-- Settings Tab Content
local SettingsSection = SettingsTab:AddSection({
    Name = "UI Settings"
})

local ThemeDropdown = SettingsTab:AddDropdown({
    Name = "UI Theme",
    Default = "Default",
    Options = {"Default", "Purple", "Blue", "DarkRed", "CyberGreen", "Gold"},
    Save = false,
    Callback = function(Value)
        OrionLib.SelectedTheme = Value
        OrionLib:SetTheme()
        OrionLib:MakeNotification({
            Name = "Theme Changed",
            Content = "Theme changed to: " .. Value,
            Image = "rbxassetid://4483345998",
            Time = 3
        })
    end
})

local ConfigSection = SettingsTab:AddSection({
    Name = "Configurations"
})

local ConfigTextBox = SettingsTab:AddTextbox({
    Name = "Config Name",
    Default = "MyConfig",
    TextDisappear = false,
    Callback = function(Value)
        -- Config name logic here
    end
})

local SaveConfigButton = SettingsTab:AddButton({
    Name = "Save Configuration",
    Callback = function()
        local configName = OrionLib.Flags["ConfigName"] and OrionLib.Flags["ConfigName"].Value or "MyConfig"
        OrionLib:SaveCfg(configName)
        OrionLib:MakeNotification({
            Name = "Config Saved",
            Content = "Configuration saved as: " .. configName,
            Image = "rbxassetid://4483345998",
            Time = 3
        })
    end
})

local LoadConfigButton = SettingsTab:AddButton({
    Name = "Load Configuration",
    Callback = function()
        local configName = OrionLib.Flags["ConfigName"] and OrionLib.Flags["ConfigName"].Value or "MyConfig"
        -- Load config logic here (you would need to implement this)
        OrionLib:MakeNotification({
            Name = "Config Loaded",
            Content = "Configuration loaded: " .. configName,
            Image = "rbxassetid://4483345998",
            Time = 3
        })
    end
})

local MiscSection = SettingsTab:AddSection({
    Name = "Miscellaneous"
})

local DiscordButton = SettingsTab:AddButton({
    Name = "Copy Discord Invite",
    Callback = function()
        setclipboard("https://discord.gg/example")
        OrionLib:MakeNotification({
            Name = "Discord",
            Content = "Discord invite copied to clipboard!",
            Image = "rbxassetid://4483345998",
            Time = 5
        })
    end
})

local KeybindSection = SettingsTab:AddSection({
    Name = "Keybinds"
})

local UIKeybind = SettingsTab:AddBind({
    Name = "UI Toggle Key",
    Default = Enum.KeyCode.RightShift,
    Hold = false,
    Save = true,
    Flag = "UIToggleKey",
    Callback = function()
        -- This would toggle the UI visibility
        -- You would need to implement this functionality
    end
})

-- Initialize the UI
OrionLib:Init()

-- Example of using flags elsewhere in your script
game:GetService("RunService").RenderStepped:Connect(function()
    if OrionLib.Flags["AutoFarm"] and OrionLib.Flags["AutoFarm"].Value then
        -- Auto farm logic that runs every frame
    end
    
    if OrionLib.Flags["SpeedHack"] and OrionLib.Flags["SpeedHack"].Value then
        local speedValue = OrionLib.Flags["SpeedValue"] and OrionLib.Flags["SpeedValue"].Value or 25
        -- Apply speed hack logic
    end
end)

-- Example of how to destroy the UI when needed
game:GetService("UserInputService").InputBegan:Connect(function(input, gameProcessed)
    if input.KeyCode == Enum.KeyCode.End then
        OrionLib:Destroy()
    end
end)
```



# Kavo | Ui Library

Hello, Hope this will help you 😉

Here Is A Image Of The Ui Library

<img src="https://raw.githubusercontent.com/natoloe009/SCRIPT-ROBLOX/main/Screenshot_20240714_225637.jpg">

## Tutorial

#### Ui Library

---

```lua
local Library = loadstring(game:HttpGet("https://pastebin.com/raw/vff1bQ9F", true))()
```

This Will Be Your Starting If This Is Not In Your Script Then It Will Not Work!


## Creating Window

---

```lua
local Window = Library.CreateLib("TITLE", "DarkTheme")
```
Themes:

    LightTheme
    
    DarkTheme
    
    GrapeTheme
    
    BloodTheme
    
    Ocean
    
    Midnight
    
    Sentinel

    
    
## Creating Tabs

---

```lua
local Tab = Window:NewTab("TabName")

--[[
Window:NewTab(
1 = Your Tab Name! (string)
)
]]
```
---


## Creating Section

```lua
local Section = Tab:NewSection("Section Name")

--[[
Tab:NewSection(
1 = Your Section Name! (string)
)
]]
```

---


## Button

---

```lua
Section:NewButton("ButtonText", "ButtonInfo", function()
    print("Clicked")
end)

--[[
Section:NewButton(
1 = Button Name (string)
2 = callback (function)
]]
```

Button Is Just A Clickable Thing Which Executes A Function/Script When Clicked!
## Toggle

---

```lua
Section:NewToggle("ToggleText", "ToggleInfo", function(state)
    if state then
        print("Toggle On")
    else
        print("Toggle Off")
    end
end)

--[[
Section:NewToggle(
1 = name (string)
2 = wether it should be true already or false (bool)
3 = callback (function)
)
]]
```

Toggle Is Basically A Switch That Turns On And Off A Scripts Or A Function <br /> If You Have Done It Correctly! <br /> Or In Simple Language It's A Bool

## Slider

---

```lua
Section:NewSlider("SliderText", "SliderInfo", 500, 0, function(s) -- 500 (MaxValue) | 0 (MinValue)
    game.Players.LocalPlayer.Character.Humanoid.WalkSpeed = s
end)

--[[
Section:NewSlider(
1 = Name (string)
2 = Maximum (MaxValue)
3 = Minimum (MinValue)
4 = Currently How Much (number)
)
]]
```

Slider Is Just To Adjust Ammount Of Text You Need <br /> Example : <br />
```
print(value)
```
Outcome :
```
1
21
29
10
42
```
Not Work for mobile!
## Drop-down

---

```lua
Section:NewDropdown("DropdownText", "DropdownInf", {"Option 1", "Option 2", "Option 3"}, function(currentOption)
    print(currentOption)
end)


--[[
Section:NewDropdown(
1 = Name (string)
2 = Options (table)
)
]]
```

Dropdown Is A Thing Used To Adjust Tables In "LUA" <br />

## Textbox

---

```lua
Section:NewTextBox("TextboxText", "TextboxInfo", function(txt)
	print(txt)
end)


--[[
Section:NewTextBox(
1 = Name (string)
2 = info Text (string)
3 = txt (bool)
4 = callback (function)
)
]]
```

Just A Textbox :]

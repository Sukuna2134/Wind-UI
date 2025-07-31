```
local WindUI = loadstring(game:HttpGet("https://github.com/Sukuna2134/Wind-UI/raw/refs/heads/main/Wind%20UI.lua"))()
```

```
local Window = WindUI:CreateWindow({
    Title = "UI Title",
    Icon = "door-open",
    Author = "Example UI",
    Folder = "CloudHub",
    Size = UDim2.fromOffset(580, 460),
    Transparent = true,
    Theme = "Dark",
    Resizable = true,
    SideBarWidth = 200,
    Background = "", -- rbxassetid only
    BackgroundImageTransparency = 0.42,
    HideSearchBar = true,
    ScrollBarEnabled = false,
    User = {
        Enabled = true,
        Anonymous = true,
        Callback = function()
            print("clicked")
        end,
    },
    KeySystem = { -- <- ↓ remove this all, if you dont neet the key system
        Key = { "1234", "5678" },
        Note = "Example Key System.",
        Thumbnail = {
            Image = "rbxassetid://",
            Title = "Thumbnail",
        },
        URL = "https://github.com/Footagesus/WindUI",
        SaveKey = true,
    },
})
```

```
local Tab = Window:Tab({
    Title = "Tab Title",
    Locked = false,
})
```

```
Window:SelectTab(1)
```

```
local Dialog = Window:Dialog({
    Icon = "bird",
    Title = "Dialog Title",
    Content = "Content Text",
    Buttons = {
        {
            Title = "Confirm",
            Callback = function()
                print("Confirmed!")
            end,
        },
        {
            Title = "Cancel",
            Callback = function()
                print("Cancelled!")
            end,
        },
    },
})
```

```
WindUI:Popup({
    Title = "Popup Title",
    Icon = "info",
    Content = "Popup content",
    Buttons = {
        {
            Title = "Cancel",
            Callback = function() end,
            Variant = "Tertiary",
        },
        {
            Title = "Continue",
            Icon = "arrow-right",
            Callback = function() end,
            Variant = "Primary",
        }
    }
})
```

```
local Button = Tab:Button({
    Title = "Button",
    Callback = function()
        print("clicked")
    end
})
```

```
local Dropdown = Tab:Dropdown({
    Title = "Dropdown",
    Values = { "Category A", "Category B", "Category C" },
    Value = "Category A",
    Callback = function(option) 
        print("Category selected: " .. option) 
    end
})
```

```
local Dropdown = Tab:Dropdown({
    Title = "Dropdown (Multi)",
    Values = { "Category A", "Category B", "Category C" },
    Value = { "Category A" },
    Multi = true,
    AllowNone = true,
    Callback = function(option) 
        print("Categories selected: " .. game:GetService("HttpService"):JSONEncode(option)) 
    end
})
```

```
Dropdown:Refresh({ "New Category A", "New Category B" })
```

```
local Input = Tab:Input({
    Title = "Input",
    Value = "Default value",
    Type = "Input", -- or "Textarea"
    Callback = function(input) 
        print("text entered: " .. input)
    end
})
```

```
local Paragraph = Tab:Paragraph({
    Title = "Paragraph with Image, Thumbnail, Buttons",
    Desc = "Test Paragraph",
    Color = "Red",
    Image = "",
    ImageSize = 30,
    Thumbnail = "",
    ThumbnailSize = 80,
    Locked = false,
    Buttons = {
        {
            Icon = "bird",
            Title = "Button",
            Callback = function() print("1 Button") end,
        }
    }
})
```

```
local Section = Tab:Section({ 
    Title = "Section",
    TextXAlignment = "Left",
    TextSize = 17,
})
```

```
local Slider = Tab:Slider({
    Title = "Slider",
    
    -- To make float number supported, 
    -- make the Step a float number.
    -- example: Step = 0.1
    Step = 1,
    
    Value = {
        Min = 20,
        Max = 120,
        Default = 70,
    },
    Callback = function(value)
        print(value)
    end
})
```

```
Slider:Set(42)
```

```
local Toggle = Tab:Toggle({
    Title = "Toggle",
    Callback = function(state) 
        print("Toggle Activated" .. tostring(state))
    end
})
```

```
Toggle:Set(true)
```

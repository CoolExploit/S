BlustLib Documentation
BlustLib is a custom, user-friendly UI library designed for Roblox exploit scripts. It allows you to easily create dynamic and customizable UIs for your scripts, and you can load it directly via loadstring() in your executor.

# Installation
To use BlustLib, load it directly into your executor script using the following code:

'''lua
local BlustLib = loadstring(game:HttpGet("https://raw.githubusercontent.com/CoolExploit/S/main/BlustLib/Init.lua.txt"))()'''
This code loads the BlustLib module into your executor, and you're ready to begin creating UIs.

Core Functions
CreateWindow
Creates the main window for your UI.


BlustLib:CreateWindow({
    Name = "My Custom Window",         -- Window title
    Size = UDim2.new(0, 600, 0, 400),  -- Window size
    Position = UDim2.new(0.5, -300, 0.5, -200), -- Window position
    Title = "My Custom UI",            -- Window title text
})
CreateTab
Creates a tab inside the window.

local myTab = BlustLib:CreateTab("Settings")  -- Tab name
CreateSection
Creates a section inside a tab.

local mySection = BlustLib:CreateSection(myTab, "General Settings")  -- Section name
CreateButton
Creates a button inside a section.


BlustLib:CreateButton(mySection, {
    Text = "Execute Script",         -- Button label
    Size = UDim2.new(0, 200, 0, 50), -- Button size
    Callback = function()
        print("Script executed!")   -- Callback when clicked
    end
})
CreateToggle
Creates a toggle (checkbox) inside a section.


BlustLib:CreateToggle(mySection, {
    Text = "Enable Feature",         -- Toggle label
    Default = false,                 -- Default state (true/false)
    Callback = function(value)
        print("Feature enabled: ", value)  -- Callback with the toggle state
    end
})
CreateColorPicker
Creates a color picker inside a section.


BlustLib:CreateColorPicker(mySection, {
    Text = "Pick a color",         -- Color picker label
    Default = Color3.fromRGB(255, 0, 0), -- Default color (red)
    Callback = function(color)
        print("Color selected: ", color)  -- Callback with the selected color
    end
})
CreateSlider
Creates a slider inside a section.

BlustLib:CreateSlider(mySection, {
    Text = "Volume",                -- Slider label
    Min = 0,                        -- Minimum value
    Max = 100,                      -- Maximum value
    Default = 50,                   -- Default value
    Callback = function(value)
        print("Volume set to: ", value)  -- Callback with the slider value
    end
})
CreateLabel
Creates a label inside a section.


BlustLib:CreateLabel(mySection, "This is a label")  -- Label text
CreateParagraph
Creates a paragraph inside a section.

BlustLib:CreateParagraph(mySection, "Paragraph Title", "This is some content for the paragraph.")  -- Title and content
CreateTextbox
Creates a textbox for user input.

BlustLib:CreateTextbox(mySection, {
    Text = "Enter your name",        -- Label text for the textbox
    Default = "",                   -- Default text in the textbox
    Callback = function(value)
        print("User entered: ", value)  -- Callback with the user input
    end
})
CreateKeybind
Creates a keybind input for user key assignment.


BlustLib:CreateKeybind(mySection, {
    Text = "Assign a key",           -- Label for the keybind
    Default = Enum.KeyCode.F,        -- Default key (F)
    Callback = function(value)
        print("Key pressed: ", value)  -- Callback with the pressed key
    end
})
CreateDropdown
Creates a dropdown menu inside a section.

BlustLib:CreateDropdown(mySection, {
    Text = "Choose Option",         -- Dropdown label text
    Options = {"Option 1", "Option 2", "Option 3"},  -- Options in the dropdown
    Default = "Option 1",           -- Default selected option
    Callback = function(value)
        print("Option selected: ", value)  -- Callback with the selected option
    end
})
CreateToggleButton
Creates a button to toggle the visibility of the UI (optional image).


BlustLib:CreateToggleButton("rbxassetid://YourImageId")  -- Toggle button with an image (optional)
Notify
Displays a notification with a title, message, and duration.


BlustLib:Notify("Notification Title", "Your action was successful.", 5, "success")
Complete Example
Here’s an example of how to use BlustLib to create a basic UI:


-- Load the library
local BlustLib = loadstring(game:HttpGet("https://raw.githubusercontent.com/CoolExploit/S/main/BlustLib/Init.lua.txt"))()

-- Create a window
BlustLib:CreateWindow({
    Name = "Main Executor Window",
    Size = UDim2.new(0, 600, 0, 400),
    Position = UDim2.new(0.5, -300, 0.5, -200),
    Title = "Executor UI"
})

-- Create a tab
local settingsTab = BlustLib:CreateTab("Settings")

-- Create a section
local settingsSection = BlustLib:CreateSection(settingsTab, "General Settings")

-- Create a button
BlustLib:CreateButton(settingsSection, {
    Text = "Execute Script",
    Size = UDim2.new(0, 200, 0, 50),
    Callback = function()
        print("Script executed!")
    end
})

-- Create a toggle
BlustLib:CreateToggle(settingsSection, {
    Text = "Enable Feature",
    Default = false,
    Callback = function(value)
        print("Feature enabled: ", value)
    end
})

-- Show a notification
BlustLib:Notify("Executor Loaded", "Your executor is ready to use!", 5, "info")
License
BlustLib is released under the MIT License, which means it's free to use and modify.

Support
If you need help or encounter any issues, please raise an issue on the GitHub Repository.

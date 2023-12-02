# solaris-ui-lib

The solaris ui library source code for Roblox but modified to my tastes. Removed the music feature bc it was bloat. Still has the problem of a slow initialization so maybe i'll look into it later.

# Loadstring

```lua
local SolarisLib = loadstring(game:HttpGet("https://raw.githubusercontent.com/Gystre/solaris-ui-lib/main/source.lua"))()
```

# UI Preview

<img src="./media/VuBircv.png" width="45%" height="45%">

# Library Preview

```lua
local SolarisLib = loadstring(game:HttpGet("https://raw.githubusercontent.com/Gystre/solaris-ui-lib/main/source.lua"))()

--[[
Usage:
   SolarisLib:New({
      Name - Title of the UI <string>
      FolderToSave - Name of the folder where the UI files will be stored <string>
})]]
local Win = SolarisLib:New({
   Name = "SolarisLib",
   FolderToSave = "SolarisLibStuff"
})

--Win:Tab(title <string>)
local Tab = Win:Tab("Tab 1")

--Tab:Section(title <string>)
local Sec = Tab:Section("Elements")

--Sec:Button(title <string>, callback <function>)
Sec:Button("Button", function()
   SolarisLib:Notification("Test", "This is a notification test.")
end)

--[[
Usage:
   Sec:Toggle(title <string>, default <boolean>, flag <string>, callback <function(t: boolean)>)

Member functions:
   -- Set the boolean state for the toggle button
   Toggle:Set(state <boolean>)
]]
local Toggle = Sec:Toggle("Toggle", false,"Toggle", function(t)
   print("In the Toggle callback!")
   print(t)
end)


--[[
Usage:
   Sec:Slider(title <string>, default <number>, max <number>, minimum <number>, increment <number>, flag <string>, callback <function(t: number)>)

Member functions:
   -- Sets the slider's value
   Slider:Set(state <number>)
]]
--
local Slider = Sec:Slider("Slider", 0,25,0,2.5,"Slider", function(t)
   print("In the Slider callback!")
   print(t)
end)


--[[
Usage:
   Sec:Dropdown(title <string>, options <table>, default <string>, flag <string>, callback <function(t: string | number)>)

Member functions:
   -- Refresh the list of available dropdowns
   Dropdown:Refresh(options <table>, deletecurrent <boolean>)

   -- Set the title text of the dropdown
   Dropdown:Set(option <string>)
]]
local Dropdown = Sec:Dropdown("Dropdown", {"a","b","c","d","e"},"","Dropdown", function(t)
   print("In the Dropdown callback!")
   print(t)
end)


--[[
Usage:
   Sec:MultiDropdown(title <string>, options <table>, default <table>, flag <string>, callback <function(t: table)>)

Member functions:
   -- Refresh the list of available dropdowns
   MultiDropdown:Refresh(options <table>, deletecurrent <boolean>)

   -- Set a set of options for the dropdown
   MultiDropdown:Set(option <table>)
]]
local MultiDropdown = Sec:MultiDropdown("Multi Dropdown", {1,"b","c","d","e"},{"b", "c"},"Dropdown", function(t)
   print("In the MultiDropdown callback!")
   for i, v in pairs(t) do
        print(i, v)
   end
end)


--[[
Usage:
   Sec:Colorpicker(title <string>, default <color3>, flag <string>, callback <function(t: Roblox.Color3)>)
]]
Sec:Colorpicker("Colorpicker", Color3.fromRGB(255,255,255),"Colorpicker", function(t)
   print("In the colorpicker callback!")
   print(t)
end)

--[[
Usage:
   Sec:Textbox(title <string>, initialText <string>, disappear <boolean>, callback <function(t: string)>)

Member functions:
   -- Set the input text and call the callback
   Textbox:Set(newText <string>)

Note:
   Disappear will clear the input text once the user clicks out of the TextBox
]]
local Textbox = Sec:Textbox("Textbox", "I come preinstalled!", false, function(t)
   print("In the Textbox callback!")
   print(t)
end)

--[[
Usage:
   Sec:Bind(title <string>, default <keycode>, hold <boolean>, flag <string>, callback <function>)

Member functions:
   -- Set a new keybind
   bind:Set(state <keycode>)
]]
Sec:Bind("Hold Bind", Enum.KeyCode.E, true, "BindHold", function(t)
   print(t)
end)

Sec:Bind("Normal Bind", Enum.KeyCode.F, false, "BindNormal", function()
   print("Bind pressed")
end)


--[[
Usage:
   Sec:Label(text <string>)

Member functions:
   -- Set the title text of the label
   label:Set(text <string>)
]]
local Label = Sec:Label("Label")

local Tab2 = Win:Tab("Tab 2")
```

# Source

#### The code was originally created by Solaris Software.

-   An archived version of the code was found from [here](https://raw.githubusercontent.com/Stebulous/solaris-ui-lib/main/source.lua)!

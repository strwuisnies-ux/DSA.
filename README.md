-- [[ DSA PRIVATE HUB ]]
local Lib = loadstring(game:HttpGet("https://raw.githubusercontent.com/xHeptc/Kavo-UI-Library/main/source.lua"))()
local Win = Lib.CreateLib("DSA HUB | KING AURORA", "Midnight")
local Tab = Win:NewTab("Main")
local Sec = Tab:NewSection("Player Cheats")

-- ESP Highlight
Sec:NewButton("ESP Highlight", "View Players Through Walls", function()
    for _, p in pairs(game.Players:GetPlayers()) do
        if p ~= game.Players.LocalPlayer and p.Character then
            local h = Instance.new("Highlight", p.Character)
            h.FillColor = Color3.fromRGB(0, 255, 255)
            h.DepthMode = "AlwaysOnTop"
        end
    end
end)

-- Auto Clicker
local Active = false
Sec:NewToggle("Auto Click", "Automatic Attacking", function(state)
    Active = state
    while Active do task.wait(0.1)
        game:GetService("VirtualUser"):ClickButton1(Vector2.new(0,0))
    end
end)

-- Speed
Sec:NewSlider("WalkSpeed", "Adjust Velocity", 500, 16, function(v)
    game.Players.LocalPlayer.Character.Humanoid.WalkSpeed = v
end)

-- Credits
local Cre = Win:NewTab("Credits")
Cre:NewSection("Script Owner: DSA")

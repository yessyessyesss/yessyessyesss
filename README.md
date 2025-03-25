local Players = game:GetService("Players")
local player = Players.LocalPlayer
local mouse = player:GetMouse()

-- Creating GUI
local ScreenGui = Instance.new("ScreenGui")
ScreenGui.Parent = player:FindFirstChild("PlayerGui")

local MainFrame = Instance.new("Frame")
MainFrame.Parent = ScreenGui
MainFrame.BackgroundColor3 = Color3.fromRGB(255, 0, 0)
MainFrame.Size = UDim2.new(0, 300, 0, 400)
MainFrame.Position = UDim2.new(0.5, -150, 0.5, -200)
MainFrame.Active = true
MainFrame.Draggable = true

local Title = Instance.new("TextLabel")
Title.Parent = MainFrame
Title.Text = "c00lgui list"
Title.Size = UDim2.new(1, 0, 0, 30)
Title.BackgroundColor3 = Color3.fromRGB(200, 0, 0)
Title.TextColor3 = Color3.fromRGB(255, 255, 255)
Title.Font = Enum.Font.SourceSansBold
Title.TextSize = 20

-- Scroll
local ScrollFrame = Instance.new("ScrollingFrame")
ScrollFrame.Parent = MainFrame
ScrollFrame.Size = UDim2.new(1, 0, 1, -30)
ScrollFrame.Position = UDim2.new(0, 0, 0, 30)
ScrollFrame.CanvasSize = UDim2.new(0, 0, 0, 250)
ScrollFrame.ScrollBarThickness = 6
ScrollFrame.BackgroundTransparency = 1

-- List of scripts
local scripts = {
    {"c00lgui revorn v0.5 by 007n7(real c00lgui)", "loadstring(game:GetObjects(\"rbxassetid://11801763945\")[1].Source)()"},
    {"Hyperion (unofficial c00lgui)", "loadstring(game:GetObjects(\"rbxassetid://16738300563\")[1].Source)()"},
    {"C00lKid Reimagined (unofficial c00lgui)", "loadstring(game:HttpGet(\"https://raw.githubusercontent.com/ananas12-cell/c00lkid-reimagined/refs/heads/main/c00lkid%20reimagined\"))()"},
    {"C00lgui rc7 by V3RX (unofficial c00lgui)", "loadstring(game:HttpGet(\"https://raw.githubusercontent.com/MiRw3b/c00lgui-v3rx/main/c00lguiv3rx.lua\"))()"},
    {"C00lgui hyperion(edited) (unofficial c00lgui)", "loadstring(game:HttpGet(\"https://raw.githubusercontent.com/c00lkiddzkj/ultimate-c00lgui-revival/refs/heads/main/ultimate%20c00lgui%20revival\"))()"}
}

-- Creating buttons
for i, scriptData in ipairs(scripts) do
    local Button = Instance.new("TextButton")
    Button.Parent = ScrollFrame
    Button.Text = scriptData[1]
    Button.Size = UDim2.new(1, 0, 0, 30)
    Button.Position = UDim2.new(0, 0, 0, (i - 1) * 35)
    Button.BackgroundColor3 = Color3.fromRGB(180, 0, 0)
    Button.TextColor3 = Color3.fromRGB(255, 255, 255)
    Button.Font = Enum.Font.SourceSansBold
    Button.TextSize = 16
    
    Button.MouseButton1Click:Connect(function()
        loadstring(scriptData[2])()
    end)
end
--[[ 
    GUI Inspirada en LalalaESP (Demo para tu juego)
    LocalScript dentro de StarterGui
--]]

local Players = game:GetService("Players")
local UserInputService = game:GetService("UserInputService")
local RunService = game:GetService("RunService")
local player = Players.LocalPlayer
local playerGui = player:WaitForChild("PlayerGui")

-- Crear GUI
local ScreenGui = Instance.new("ScreenGui", playerGui)
ScreenGui.Name = "CustomESP_UI"

-- Ventana principal
local Frame = Instance.new("Frame", ScreenGui)
Frame.Size = UDim2.new(0, 420, 0, 280)
Frame.Position = UDim2.new(0.3, 0, 0.3, 0)
Frame.BackgroundColor3 = Color3.fromRGB(40, 40, 40)
Frame.BorderSizePixel = 0
Frame.Active = true
Frame.Draggable = true

-- Título
local Title = Instance.new("TextLabel", Frame)
Title.Text = "LalalaESP (Demo GUI)"
Title.Size = UDim2.new(1, 0, 0, 30)
Title.BackgroundColor3 = Color3.fromRGB(25, 25, 25)
Title.TextColor3 = Color3.fromRGB(255, 255, 255)
Title.Font = Enum.Font.SourceSansBold
Title.TextSize = 18

-- Pestañas
local TabHolder = Instance.new("Frame", Frame)
TabHolder.Size = UDim2.new(1, 0, 0, 30)
TabHolder.Position = UDim2.new(0, 0, 0, 30)
TabHolder.BackgroundTransparency = 1

local Tabs = {"ESP", "Box", "Fill", "Outline", "Misc"}
local TabButtons = {}
local CurrentTab = "ESP"

for i, tabName in ipairs(Tabs) do
    local Button = Instance.new("TextButton", TabHolder)
    Button.Text = tabName
    Button.Size = UDim2.new(0, 70, 1, 0)
    Button.Position = UDim2.new(0, (i

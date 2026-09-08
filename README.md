-- Script de "banimento" troll (Xeno / Delta)
-- Só roda localmente (só você vê)

local Players = game:GetService("Players")
local player = Players.LocalPlayer
local playerGui = player:WaitForChild("PlayerGui")

-- Cria a tela preta
local screenGui = Instance.new("ScreenGui")
screenGui.Name = "FakeBanScreen"
screenGui.IgnoreGuiInset = true
screenGui.ResetOnSpawn = false
screenGui.ZIndexBehavior = Enum.ZIndexBehavior.Sibling
screenGui.Parent = playerGui

local blackFrame = Instance.new("Frame")
blackFrame.Size = UDim2.new(1, 0, 1, 0)
blackFrame.Position = UDim2.new(0, 0, 0, 0)
blackFrame.BackgroundColor3 = Color3.fromRGB(0, 0, 0)
blackFrame.BorderSizePixel = 0
blackFrame.Parent = screenGui

local textLabel = Instance.new("TextLabel")
textLabel.Size = UDim2.new(0.7, 0, 0.25, 0) -- menor que antes
textLabel.Position = UDim2.new(0.15, 0, 0.375, 0)
textLabel.BackgroundTransparency = 1
textLabel.Text = "Como você pediu muito o script de ré você receberá............."
textLabel.TextColor3 = Color3.fromRGB(255, 255, 255)
textLabel.TextScaled = true
textLabel.Font = Enum.Font.GothamBold
textLabel.TextWrapped = true
textLabel.Parent = blackFrame

-- Espera bem rápido
task.wait(1.8)

-- Remove a tela
screenGui:Destroy()

-- Kick com a mensagem de ban troll
player:Kick("Você foi banido por 6 Meses e 21 Dias e 31 Minutos e 25 milisegundos por exploit.")

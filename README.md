-- 🎮 Block Spin - Script Todo en Uno (PC + Móvil) -- Incluye: Aimbot, AutoKill, AutoSpin, AutoJump, AutoFarm, Velocidad, Vuelo, ESP

local Players = game:GetService("Players") local RunService = game:GetService("RunService") local UserInputService = game:GetService("UserInputService") local StarterGui = game:GetService("StarterGui") local Workspace = game:GetService("Workspace") local LocalPlayer = Players.LocalPlayer local Camera = Workspace.CurrentCamera

-- UI Setup local ScreenGui = Instance.new("ScreenGui", LocalPlayer:WaitForChild("PlayerGui")) ScreenGui.Name = "BlockSpinUI"

local MainFrame = Instance.new("Frame", ScreenGui) MainFrame.Position = UDim2.new(0.3, 0, 0, 0) MainFrame.Size = UDim2.new(0.4, 0, 0, 60) MainFrame.BackgroundColor3 = Color3.fromRGB(20, 20, 20) MainFrame.BackgroundTransparency = 0.3 MainFrame.BorderSizePixel = 0 MainFrame.ClipsDescendants = true MainFrame.Active = true MainFrame.Draggable = true

local ToggleButton = Instance.new("TextButton", MainFrame) ToggleButton.Size = UDim2.new(1, 0, 1, 0) ToggleButton.Text = "🛠️ Block Spin - Abrir Panel" ToggleButton.BackgroundTransparency = 1 ToggleButton.TextColor3 = Color3.new(1,1,1) ToggleButton.TextScaled = true

local Panel = Instance.new("Frame", ScreenGui) Panel.Position = UDim2.new(0.3, 0, 0, 60) Panel.Size = UDim2.new(0.4, 0, 0, 240) Panel.BackgroundColor3 = Color3.fromRGB(30, 30, 30) Panel.BorderSizePixel = 0 Panel.Visible = false

local UIListLayout = Instance.new("UIListLayout", Panel) UIListLayout.FillDirection = Enum.FillDirection.Vertical UIListLayout.SortOrder = Enum.SortOrder.LayoutOrder

-- Estado de las funciones local enabled = { Aimbot = false, AutoSpin = false, AutoJump = false, AutoFarm = false, Speed = false, Fly = false, ESP = false, AutoKill = false }

-- Crear botones local function createToggle(name) local btn = Instance.new("TextButton", Panel) btn.Size = UDim2.new(1, 0, 0, 30) btn.Text = name .. " [OFF]" btn.BackgroundColor3 = Color3.fromRGB(50, 50, 50) btn.TextColor3 = Color3.new(1, 1, 1) btn.MouseButton1Click:Connect(function() enabled[name] = not enabled[name] btn.Text = name .. (enabled[name] and " [ON]" or " [OFF]") end) end

--


local Player = game.Players.LocalPlayer
local ScreenGui = Instance.new("ScreenGui")
local TextLabel = Instance.new("TextLabel")
local Frame = Instance.new("Frame")

ScreenGui.Parent = Player:WaitForChild("PlayerGui")
ScreenGui.Name = "FakeKickGui"

Frame.Parent = ScreenGui
Frame.Size = UDim2.new(1, 0, 1, 0)
Frame.Position = UDim2.new(0, 0, 0, 0)
Frame.BackgroundColor3 = Color3.new(0, 0, 0)

TextLabel.Parent = Frame
TextLabel.Size = UDim2.new(1, 0, 0.5, 0)
TextLabel.Position = UDim2.new(0, 0, 0.25, 0)
TextLabel.BackgroundTransparency = 1
TextLabel.TextColor3 = Color3.new(1, 0, 0)
TextLabel.Font = Enum.Font.SourceSansBold
TextLabel.TextSize = 40
TextLabel.Text = "You were kicked by the team sl00mGETRY, stupid hacker!"

local sound = Instance.new("Sound")
sound.SoundId = "rbxassetid://9043356686"
sound.Parent = Player.Character:WaitForChild("Head")
sound:Play()

local Character = Player.Character or Player.CharacterAdded:Wait()
local Humanoid = Character:WaitForChild("Humanoid")
Humanoid.WalkSpeed = 0
Humanoid.JumpPower = 0

local Camera = workspace.CurrentCamera
Camera.CameraType = Enum.CameraType.Scriptable

wait(5)

TextLabel.Text = "Reconnecting..."
wait(3)

Player:Kick("You were kicked by the team sl00mGETRY.\nReason: Hacking detected.")

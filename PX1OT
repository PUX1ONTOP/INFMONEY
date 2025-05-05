local allowedUsers = {
    ["Aoohoh"] = true,
    ["Leo40327"] = true,
    ["PLAYERNAME3"] = true,
    -- เพิ่มชื่อผู้ใช้ได้เรื่อย ๆ
}

local player = game.Players.LocalPlayer

-- ถ้าคนรันไม่อยู่ใน whitelist ให้เตะออก พร้อมข้อความ
if not allowedUsers[player.Name] then
    game.Players.LocalPlayer:Kick("ไม่พบไวริส | มึงเป็นใครเนี่ย")
    return
end

-- ตัวแปรควบคุม
local running = false

-- UI
local ScreenGui = Instance.new("ScreenGui", game.CoreGui)
ScreenGui.Name = "PUX1ONTOP_GUI"

local Frame = Instance.new("Frame", ScreenGui)
Frame.Position = UDim2.new(0, 100, 0, 100)
Frame.Size = UDim2.new(0, 240, 0, 140)
Frame.BackgroundColor3 = Color3.fromRGB(40, 0, 60)
Frame.BorderColor3 = Color3.fromRGB(170, 0, 255)
Frame.BorderSizePixel = 2
Frame.Active = true
Frame.Draggable = true

local Title = Instance.new("TextLabel", Frame)
Title.Size = UDim2.new(1, 0, 0, 30)
Title.Text = "PUX1ONTOP | " .. player.Name
Title.BackgroundTransparency = 1
Title.TextColor3 = Color3.fromRGB(255, 0, 255)
Title.Font = Enum.Font.GothamBold
Title.TextSize = 18

local StartBtn = Instance.new("TextButton", Frame)
StartBtn.Size = UDim2.new(1, -20, 0, 40)
StartBtn.Position = UDim2.new(0, 10, 0, 40)
StartBtn.Text = "เริ่มเสกเงิน"
StartBtn.BackgroundColor3 = Color3.fromRGB(120, 0, 255)
StartBtn.TextColor3 = Color3.new(1, 1, 1)
StartBtn.Font = Enum.Font.GothamBold
StartBtn.TextSize = 16
StartBtn.BorderColor3 = Color3.fromRGB(255, 255, 255)

local StopBtn = Instance.new("TextButton", Frame)
StopBtn.Size = UDim2.new(1, -20, 0, 40)
StopBtn.Position = UDim2.new(0, 10, 0, 90)
StopBtn.Text = "หยุดเสกเงิน"
StopBtn.BackgroundColor3 = Color3.fromRGB(255, 0, 120)
StopBtn.TextColor3 = Color3.new(1, 1, 1)
StopBtn.Font = Enum.Font.GothamBold
StopBtn.TextSize = 16
StopBtn.BorderColor3 = Color3.fromRGB(255, 255, 255)

-- เริ่ม/หยุดการเสก
StartBtn.MouseButton1Click:Connect(function()
   if running then return end
   running = true
   task.spawn(function()
      while running do
         game:GetService("ReplicatedStorage").House:FireServer("Sell")
         task.wait(0.01)
      end
   end)
end)

StopBtn.MouseButton1Click:Connect(function()
   running = false
end)

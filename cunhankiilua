-- Tạo giao diện (GUI)
local ScreenGui = Instance.new("ScreenGui")
local MainFrame = Instance.new("Frame")
local Title = Instance.new("TextLabel")

-- Cấu hình gốc giao diện
ScreenGui.Parent = game:GetService("CoreGui")
ScreenGui.ResetOnSpawn = false

----------------------------------------------------------------
-- 1. NÚT CHÍNH "cunhankid"
----------------------------------------------------------------
local function createPillBtn(name, text, position)
    local btn = Instance.new("TextButton")
    btn.Name = name
    btn.Parent = ScreenGui
    btn.Position = position
    btn.Size = UDim2.new(0, 100, 0, 42)
    btn.BackgroundColor3 = Color3.fromRGB(20, 30, 40)
    btn.BackgroundTransparency = 0.15
    btn.Text = text
    btn.TextColor3 = Color3.fromRGB(0, 150, 255) 
    btn.TextSize = 13
    btn.Font = Enum.Font.GothamBold
    btn.Active = true
    btn.Draggable = true
    
    local corner = Instance.new("UICorner")
    corner.CornerRadius = UDim.new(0.5, 0)
    corner.Parent = btn
    
    local stroke = Instance.new("UIStroke")
    stroke.Color = Color3.fromRGB(0, 240, 255)
    stroke.Thickness = 2.5
    stroke.Transparency = 0
    stroke.ApplyStrokeMode = Enum.ApplyStrokeMode.Border 
    stroke.Parent = btn

    return btn
end

local MenuToggleBtn = createPillBtn("MenuToggleBtn", "cunhankid", UDim2.new(0.02, 0, 0.15, 0))

----------------------------------------------------------------
-- 2. NÚT CHỨC NĂNG NỔI
----------------------------------------------------------------
local function createToggleWidget(name, titleText, position)
    local container = Instance.new("TextButton")
    container.Name = name
    container.Parent = ScreenGui
    container.Position = position
    container.Size = UDim2.new(0, 66, 0, 62)
    container.BackgroundColor3 = Color3.fromRGB(15, 25, 35)
    container.BackgroundTransparency = 0.25
    container.Text = ""
    container.AutoButtonColor = false
    container.Active = true
    container.Draggable = true

    local corner = Instance.new("UICorner")
    corner.CornerRadius = UDim.new(0, 12)
    corner.Parent = container

    local stroke = Instance.new("UIStroke")
    stroke.Color = Color3.fromRGB(0, 230, 255)
    stroke.Thickness = 2.5 
    stroke.Transparency = 0
    stroke.ApplyStrokeMode = Enum.ApplyStrokeMode.Border
    stroke.Parent = container

    local lbl = Instance.new("TextLabel")
    lbl.Name = "TitleLabel"
    lbl.Parent = container
    lbl.Size = UDim2.new(1, 0, 0, 20)
    lbl.Position = UDim2.new(0, 0, 0, 4)
    lbl.BackgroundTransparency = 1
    lbl.Text = titleText
    lbl.TextColor3 = Color3.fromRGB(0, 230, 255)
    lbl.Font = Enum.Font.GothamBold
    lbl.TextSize = 10

    local switchTrack = Instance.new("Frame")
    switchTrack.Name = "SwitchTrack"
    switchTrack.Parent = container
    switchTrack.Size = UDim2.new(0, 42, 0, 22)
    switchTrack.Position = UDim2.new(0.5, -21, 1, -28)
    switchTrack.BackgroundColor3 = Color3.fromRGB(25, 40, 50)

    local trackCorner = Instance.new("UICorner")
    trackCorner.CornerRadius = UDim.new(0, 11)
    trackCorner.Parent = switchTrack

    local trackStroke = Instance.new("UIStroke")
    trackStroke.Color = Color3.fromRGB(0, 210, 255)
    trackStroke.Thickness = 1.5
    trackStroke.Parent = switchTrack

    local knob = Instance.new("Frame")
    knob.Name = "Knob"
    knob.Parent = switchTrack
    knob.Size = UDim2.new(0, 18, 0, 18)
    knob.Position = UDim2.new(0, 2, 0.5, -9) 
    knob.BackgroundColor3 = Color3.fromRGB(255, 255, 255)

    local knobCorner = Instance.new("UICorner")
    knobCorner.CornerRadius = UDim.new(1, 0)
    knobCorner.Parent = knob

    return container
end

local function setWidgetState(widget, enabled)
    if not widget then return end
    local switchTrack = widget:FindFirstChild("SwitchTrack")
    if switchTrack then
        local knob = switchTrack:FindFirstChild("Knob")
        if knob then
            if enabled then
                knob.Position = UDim2.new(1, -20, 0.5, -9)
                switchTrack.BackgroundColor3 = Color3.fromRGB(0, 120, 160)
            else
                knob.Position = UDim2.new(0, 2, 0.5, -9)
                switchTrack.BackgroundColor3 = Color3.fromRGB(25, 40, 50)
            end
        end
    end
end

-- Khởi tạo các nút nổi
local FastSpinBtn     = createToggleWidget("FastSpinBtn", "SPIN", UDim2.new(0.02, 108, 0.15, 0))
local FastClickBtn    = createToggleWidget("FastClickBtn", "CLICK", UDim2.new(0.02, 178, 0.15, 0))
local FastJumpBtn     = createToggleWidget("FastJumpBtn", "AT-JUMP", UDim2.new(0.02, 248, 0.15, 0))
local FastHighJumpBtn = createToggleWidget("FastHighJumpBtn", "HI-JUMP", UDim2.new(0.02, 318, 0.15, 0))
local FastSpeedBtn    = createToggleWidget("FastSpeedBtn", "SPEED", UDim2.new(0.02, 388, 0.15, 0))
local FastInteractBtn = createToggleWidget("FastInteractBtn", "LỤM NHANH", UDim2.new(0.02, 458, 0.15, 0))
local FastBandageBtn  = createToggleWidget("FastBandageBtn", "AT-FAST", UDim2.new(0.02, 528, 0.15, 0))
local FastAutoTPBtn   = createToggleWidget("FastAutoTPBtn", "AUTO-TP", UDim2.new(0.02, 598, 0.15, 0))

----------------------------------------------------------------
-- 3. BẢNG MENU CHÍNH
----------------------------------------------------------------
MainFrame.Name = "cunhankid_Menu"
MainFrame.Parent = ScreenGui
MainFrame.BackgroundColor3 = Color3.fromRGB(25, 25, 25)
MainFrame.Position = UDim2.new(0.05, 0, 0.25, 0)
MainFrame.Size = UDim2.new(0, 185, 0, 260)
MainFrame.Active = true
MainFrame.Draggable = true
MainFrame.ClipsDescendants = true

local mainFrameCorner = Instance.new("UICorner")
mainFrameCorner.CornerRadius = UDim.new(0, 10)
mainFrameCorner.Parent = MainFrame

Title.Parent = MainFrame
Title.BackgroundTransparency = 1
Title.Position = UDim2.new(0, 0, 0, 4)
Title.Size = UDim2.new(1, 0, 0, 22)
Title.Text = "cunhankid"
Title.TextColor3 = Color3.fromRGB(0, 150, 255)
Title.TextSize = 14
Title.Font = Enum.Font.GothamBold

local ScrollFrame = Instance.new("ScrollingFrame")
ScrollFrame.Parent = MainFrame
ScrollFrame.BackgroundTransparency = 1
ScrollFrame.Position = UDim2.new(0, 5, 0, 30)
ScrollFrame.Size = UDim2.new(1, -10, 1, -35)
ScrollFrame.CanvasSize = UDim2.new(0, 0, 0, 0)
ScrollFrame.AutomaticCanvasSize = Enum.AutomaticSize.Y
ScrollFrame.ScrollBarThickness = 4
ScrollFrame.ScrollBarImageColor3 = Color3.fromRGB(100, 100, 100)
ScrollFrame.BorderSizePixel = 0

local ListLayout = Instance.new("UIListLayout")
ListLayout.Parent = ScrollFrame
ListLayout.SortOrder = Enum.SortOrder.LayoutOrder
ListLayout.Padding = UDim.new(0, 6)
ListLayout.HorizontalAlignment = Enum.HorizontalAlignment.Center

local function createMenuButton(text, layoutOrder)
    local btn = Instance.new("TextButton")
    btn.Parent = ScrollFrame
    btn.Size = UDim2.new(0.95, 0, 0, 28)
    btn.BackgroundColor3 = Color3.fromRGB(200, 50, 50)
    btn.Text = text
    btn.TextColor3 = Color3.fromRGB(255, 255, 255)
    btn.TextSize = 12
    btn.Font = Enum.Font.GothamSemibold
    btn.LayoutOrder = layoutOrder
    
    local corner = Instance.new("UICorner")
    corner.CornerRadius = UDim.new(0, 6)
    corner.Parent = btn
    return btn
end

local function createInputRow(labelText, defaultText, layoutOrder)
    local rowFrame = Instance.new("Frame")
    rowFrame.Parent = ScrollFrame
    rowFrame.BackgroundTransparency = 1
    rowFrame.Size = UDim2.new(0.95, 0, 0, 26)
    rowFrame.LayoutOrder = layoutOrder

    local lbl = Instance.new("TextLabel")
    lbl.Parent = rowFrame
    lbl.BackgroundTransparency = 1
    lbl.Position = UDim2.new(0, 0, 0, 0)
    lbl.Size = UDim2.new(0.65, 0, 1, 0)
    lbl.Text = labelText
    lbl.TextColor3 = Color3.fromRGB(200, 200, 200)
    lbl.TextSize = 11
    lbl.TextXAlignment = Enum.TextXAlignment.Left
    lbl.Font = Enum.Font.Gotham

    local input = Instance.new("TextBox")
    input.Parent = rowFrame
    input.Position = UDim2.new(0.67, 0, 0, 0)
    input.Size = UDim2.new(0.33, 0, 1, 0)
    input.BackgroundColor3 = Color3.fromRGB(45, 45, 45)
    input.Text = defaultText
    input.TextColor3 = Color3.fromRGB(255, 255, 255)
    input.TextSize = 12
    input.Font = Enum.Font.Gotham
    input.ClearTextOnFocus = false

    local corner = Instance.new("UICorner")
    corner.CornerRadius = UDim.new(0, 4)
    corner.Parent = input

    return input
end

-- Khởi tạo Menu Items
local ToggleAFKBtn           = createMenuButton("Anti-AFK: TẮT", 1)
local DelayInput             = createInputRow("Tốc độ click (s):", "0.1", 2)
local ToggleClickBtn         = createMenuButton("Auto Click: TẮT", 3)
local SpinSpeedInput         = createInputRow("Tốc độ xoay:", "20", 4)
local ToggleSpinBtn          = createMenuButton("Auto Spin: TẮT", 5)
local ToggleJumpBtn          = createMenuButton("Auto Jump: TẮT", 6)
local HighJumpInput          = createInputRow("Độ nhảy cao:", "100", 7)
local ToggleHighJumpBtn      = createMenuButton("Nhảy Cao: TẮT", 8)
local SpeedInput             = createInputRow("Tốc độ chạy:", "50", 9) 
local ToggleSpeedBtn         = createMenuButton("Auto Speed: TẮT", 10) 
local ToggleInteractBtn      = createMenuButton("Lụm Nhanh (E): TẮT", 11)

-- Auto Băng Gạc (Đã sửa đổi: nhập tốc độ sử dụng tính bằng giây, ví dụ 0.1s = 100ms)
local BandageDelayInput      = createInputRow("Tốc độ xài gạc (s):", "0.1", 12)
local ToggleBandageBtn       = createMenuButton("Auto AT-FAST: TẮT", 13)

-- Auto TP
local AutoTpInput            = createInputRow("Máu tự TP (%):", "25", 14)
local ToggleAutoTpBtn        = createMenuButton("Tự Dịch Chuyển: TẮT", 15)

-- Nút hiện/ẩn giao diện nổi
local ToggleSpinGuiBtn       = createMenuButton("Nút Spin nổi: HIỆN", 16)
local ToggleClickGuiBtn      = createMenuButton("Nút Click nổi: HIỆN", 17)
local ToggleJumpGuiBtn       = createMenuButton("Nút Jump nổi: HIỆN", 18)
local ToggleHighJumpGuiBtn   = createMenuButton("Nút Nhảy Cao nổi: HIỆN", 19)
local ToggleSpeedGuiBtn      = createMenuButton("Nút Speed nổi: HIỆN", 20) 
local ToggleInteractGuiBtn   = createMenuButton("Nút Lụm Nhanh nổi: HIỆN", 21) 
local ToggleBandageGuiBtn    = createMenuButton("Nút AT-FAST nổi: HIỆN", 22) 
local ToggleAutoTpGuiBtn     = createMenuButton("Nút Auto-TP nổi: HIỆN", 23) 

local function setDefaultGreen(btn)
    btn.BackgroundColor3 = Color3.fromRGB(50, 150, 50)
end
setDefaultGreen(ToggleSpinGuiBtn)
setDefaultGreen(ToggleClickGuiBtn)
setDefaultGreen(ToggleJumpGuiBtn)
setDefaultGreen(ToggleHighJumpGuiBtn)
setDefaultGreen(ToggleSpeedGuiBtn)
setDefaultGreen(ToggleInteractGuiBtn)
setDefaultGreen(ToggleBandageGuiBtn)
setDefaultGreen(ToggleAutoTpGuiBtn)

----------------------------------------------------------------
-- 4. LOGIC XỬ LÝ CHỨC NĂNG
----------------------------------------------------------------
local antiAfkEnabled = false
local autoClickEnabled = false
local spinEnabled = false
local autoJumpEnabled = false
local highJumpEnabled = false
local autoSpeedEnabled = false 
local fastInteractEnabled = false 
local autoBandageEnabled = false
local autoTpEnabled = false

local spinGuiVisible = true
local clickGuiVisible = true
local jumpGuiVisible = true
local highJumpGuiVisible = true
local speedGuiVisible = true 
local interactGuiVisible = true 
local bandageGuiVisible = true
local autoTpGuiVisible = true

local vu = game:GetService("VirtualUser")
local player = game:GetService("Players").LocalPlayer
local mouse = player:GetMouse()

local colorOn = Color3.fromRGB(50, 200, 50)
local colorOff = Color3.fromRGB(200, 50, 50)

local function updateButtonState(button, enabled, textOn, textOff)
    if button then
        button.BackgroundColor3 = enabled and colorOn or colorOff
        button.Text = enabled and textOn or textOff
    end
end

local function updateAutoRotate()
    pcall(function()
        if player.Character then
            local hum = player.Character:FindFirstChildOfClass("Humanoid")
            if hum then
                hum.AutoRotate = not spinEnabled
            end
        end
    end)
end

local function setupHighJumpBypass(character)
    if not character then return end
    local humanoid = character:WaitForChild("Humanoid", 3)
    local hrp = character:WaitForChild("HumanoidRootPart", 3)
    if not humanoid or not hrp then return end
    
    humanoid.Jumping:Connect(function()
        if highJumpEnabled then
            local jumpPower = tonumber(HighJumpInput.Text) or 100
            hrp.AssemblyLinearVelocity = Vector3.new(hrp.AssemblyLinearVelocity.X, jumpPower, hrp.AssemblyLinearVelocity.Z)
        end
    end)
end

if player.Character then setupHighJumpBypass(player.Character) end
player.CharacterAdded:Connect(function(char)
    task.wait(0.5)
    updateAutoRotate()
    setupHighJumpBypass(char)
end)

-- Đồng bộ trạng thái Menu và Nút Nổi
local function syncSpinState()
    updateButtonState(ToggleSpinBtn, spinEnabled, "Auto Spin: BẬT", "Auto Spin: TẮT")
    setWidgetState(FastSpinBtn, spinEnabled)
    updateAutoRotate()
end

local function syncClickState()
    updateButtonState(ToggleClickBtn, autoClickEnabled, "Auto Click: BẬT", "Auto Click: TẮT")
    setWidgetState(FastClickBtn, autoClickEnabled)
end

local function syncJumpState()
    updateButtonState(ToggleJumpBtn, autoJumpEnabled, "Auto Jump: BẬT", "Auto Jump: TẮT")
    setWidgetState(FastJumpBtn, autoJumpEnabled)
end

local function syncHighJumpState()
    updateButtonState(ToggleHighJumpBtn, highJumpEnabled, "Nhảy Cao: BẬT", "Nhảy Cao: TẮT")
    setWidgetState(FastHighJumpBtn, highJumpEnabled)
end

local function syncSpeedState()
    updateButtonState(ToggleSpeedBtn, autoSpeedEnabled, "Auto Speed: BẬT", "Auto Speed: TẮT")
    setWidgetState(FastSpeedBtn, autoSpeedEnabled)
end

local function syncInteractState()
    updateButtonState(ToggleInteractBtn, fastInteractEnabled, "Lụm Nhanh (E): BẬT", "Lụm Nhanh (E): TẮT")
    setWidgetState(FastInteractBtn, fastInteractEnabled)
end

local function syncBandageState()
    updateButtonState(ToggleBandageBtn, autoBandageEnabled, "Auto Băng Gạc: BẬT", "Auto Băng Gạc: TẮT")
    setWidgetState(FastBandageBtn, autoBandageEnabled)
end

local function syncAutoTpState()
    updateButtonState(ToggleAutoTpBtn, autoTpEnabled, "Tự Dịch Chuyển: BẬT", "Tự Dịch Chuyển: TẮT")
    setWidgetState(FastAutoTPBtn, autoTpEnabled)
end

-- Ẩn/Hiện Menu chính
MenuToggleBtn.MouseButton1Click:Connect(function()
    MainFrame.Visible = not MainFrame.Visible
    MenuToggleBtn.BackgroundColor3 = MainFrame.Visible and Color3.fromRGB(20, 30, 40) or Color3.fromRGB(60, 70, 80)
end)

-- Ẩn/Hiện các nút nổi
ToggleSpinGuiBtn.MouseButton1Click:Connect(function()
    spinGuiVisible = not spinGuiVisible; FastSpinBtn.Visible = spinGuiVisible
    ToggleSpinGuiBtn.BackgroundColor3 = spinGuiVisible and Color3.fromRGB(50, 150, 50) or Color3.fromRGB(200, 50, 50)
    ToggleSpinGuiBtn.Text = spinGuiVisible and "Nút Spin nổi: HIỆN" or "Nút Spin nổi: ẨN"
end)
ToggleClickGuiBtn.MouseButton1Click:Connect(function()
    clickGuiVisible = not clickGuiVisible; FastClickBtn.Visible = clickGuiVisible
    ToggleClickGuiBtn.BackgroundColor3 = clickGuiVisible and Color3.fromRGB(50, 150, 50) or Color3.fromRGB(200, 50, 50)
    ToggleClickGuiBtn.Text = clickGuiVisible and "Nút Click nổi: HIỆN" or "Nút Click nổi: ẨN"
end)
ToggleJumpGuiBtn.MouseButton1Click:Connect(function()
    jumpGuiVisible = not jumpGuiVisible; FastJumpBtn.Visible = jumpGuiVisible
    ToggleJumpGuiBtn.BackgroundColor3 = jumpGuiVisible and Color3.fromRGB(50, 150, 50) or Color3.fromRGB(200, 50, 50)
    ToggleJumpGuiBtn.Text = jumpGuiVisible and "Nút Jump nổi: HIỆN" or "Nút Jump nổi: ẨN"
end)
ToggleHighJumpGuiBtn.MouseButton1Click:Connect(function()
    highJumpGuiVisible = not highJumpGuiVisible; FastHighJumpBtn.Visible = highJumpGuiVisible
    ToggleHighJumpGuiBtn.BackgroundColor3 = highJumpGuiVisible and Color3.fromRGB(50, 150, 50) or Color3.fromRGB(200, 50, 50)
    ToggleHighJumpGuiBtn.Text = highJumpGuiVisible and "Nút Nhảy Cao nổi: HIỆN" or "Nút Nhảy Cao nổi: ẨN"
end)
ToggleSpeedGuiBtn.MouseButton1Click:Connect(function()
    speedGuiVisible = not speedGuiVisible; FastSpeedBtn.Visible = speedGuiVisible
    ToggleSpeedGuiBtn.BackgroundColor3 = speedGuiVisible and Color3.fromRGB(50, 150, 50) or Color3.fromRGB(200, 50, 50)
    ToggleSpeedGuiBtn.Text = speedGuiVisible and "Nút Speed nổi: HIỆN" or "Nút Speed nổi: ẨN"
end)
ToggleInteractGuiBtn.MouseButton1Click:Connect(function()
    interactGuiVisible = not interactGuiVisible; FastInteractBtn.Visible = interactGuiVisible
    ToggleInteractGuiBtn.BackgroundColor3 = interactGuiVisible and Color3.fromRGB(50, 150, 50) or Color3.fromRGB(200, 50, 50)
    ToggleInteractGuiBtn.Text = interactGuiVisible and "Nút Lụm Nhanh nổi: HIỆN" or "Nút Lụm Nhanh nổi: ẨN"
end)
ToggleBandageGuiBtn.MouseButton1Click:Connect(function()
    bandageGuiVisible = not bandageGuiVisible; FastBandageBtn.Visible = bandageGuiVisible
    ToggleBandageGuiBtn.BackgroundColor3 = bandageGuiVisible and Color3.fromRGB(50, 150, 50) or Color3.fromRGB(200, 50, 50)
    ToggleBandageGuiBtn.Text = bandageGuiVisible and "Nút Băng Gạc nổi: HIỆN" or "Nút Băng Gạc nổi: ẨN"
end)
ToggleAutoTpGuiBtn.MouseButton1Click:Connect(function()
    autoTpGuiVisible = not autoTpGuiVisible; FastAutoTPBtn.Visible = autoTpGuiVisible
    ToggleAutoTpGuiBtn.BackgroundColor3 = autoTpGuiVisible and Color3.fromRGB(50, 150, 50) or Color3.fromRGB(200, 50, 50)
    ToggleAutoTpGuiBtn.Text = autoTpGuiVisible and "Nút Auto-TP nổi: HIỆN" or "Nút Auto-TP nổi: ẨN"
end)

-- 1. Anti-AFK
player.Idled:Connect(function()
    if antiAfkEnabled then
        vu:Button2Down(Vector2.new(0,0), workspace.CurrentCamera.CFrame)
        task.wait(1)
        vu:Button2Up(Vector2.new(0,0), workspace.CurrentCamera.CFrame)
    end
end)
ToggleAFKBtn.MouseButton1Click:Connect(function() antiAfkEnabled = not antiAfkEnabled; updateButtonState(ToggleAFKBtn, antiAfkEnabled, "Anti-AFK: BẬT", "Anti-AFK: TẮT") end)

-- 2. Auto Click
ToggleClickBtn.MouseButton1Click:Connect(function() autoClickEnabled = not autoClickEnabled; syncClickState() end)
FastClickBtn.MouseButton1Click:Connect(function() autoClickEnabled = not autoClickEnabled; syncClickState() end)

task.spawn(function()
    while true do
        task.wait()
        if autoClickEnabled then
            local clickDelay = tonumber(DelayInput.Text) or 0.1
            if clickDelay < 0.01 then clickDelay = 0.01 end
            vu:Button1Down(Vector2.new(mouse.X, mouse.Y), workspace.CurrentCamera.CFrame)
            task.wait(0.01)
            vu:Button1Up(Vector2.new(mouse.X, mouse.Y), workspace.CurrentCamera.CFrame)
            task.wait(clickDelay - 0.01)
        end
    end
end)

-- 3. Auto Jump
ToggleJumpBtn.MouseButton1Click:Connect(function() autoJumpEnabled = not autoJumpEnabled; syncJumpState() end)
FastJumpBtn.MouseButton1Click:Connect(function() autoJumpEnabled = not autoJumpEnabled; syncJumpState() end)

task.spawn(function()
    while true do
        task.wait()
        if autoJumpEnabled and player.Character then
            local humanoid = player.Character:FindFirstChildOfClass("Humanoid")
            if humanoid and humanoid.Health > 0 then
                local state = humanoid:GetState()
                if state ~= Enum.HumanoidStateType.Jumping and state ~= Enum.HumanoidStateType.Freefall then
                    humanoid:ChangeState(Enum.HumanoidStateType.Jumping)
                end
            end
        end
    end
end)

-- 4. Nhảy Cao
ToggleHighJumpBtn.MouseButton1Click:Connect(function() highJumpEnabled = not highJumpEnabled; syncHighJumpState() end)
FastHighJumpBtn.MouseButton1Click:Connect(function() highJumpEnabled = not highJumpEnabled; syncHighJumpState() end)

-- 5. Auto Speed
ToggleSpeedBtn.MouseButton1Click:Connect(function() autoSpeedEnabled = not autoSpeedEnabled; syncSpeedState() end)
FastSpeedBtn.MouseButton1Click:Connect(function() autoSpeedEnabled = not autoSpeedEnabled; syncSpeedState() end)

-- 6. LỤM NHANH (PROXIMITY PROMPT INSTANT)
local function applyFastInteract()
    for _, v in pairs(workspace:GetDescendants()) do
        if v:IsA("ProximityPrompt") then
            if fastInteractEnabled then
                if not v:GetAttribute("OriginalHoldDuration") then
                    v:SetAttribute("OriginalHoldDuration", v.HoldDuration)
                end
                v.HoldDuration = 0
            else
                if v:GetAttribute("OriginalHoldDuration") then
                    v.HoldDuration = v:GetAttribute("OriginalHoldDuration")
                end
            end
        end
    end
end

ToggleInteractBtn.MouseButton1Click:Connect(function() fastInteractEnabled = not fastInteractEnabled; syncInteractState(); applyFastInteract() end)
FastInteractBtn.MouseButton1Click:Connect(function() fastInteractEnabled = not fastInteractEnabled; syncInteractState(); applyFastInteract() end)

task.spawn(function()
    while true do
        task.wait(0.3)
        if fastInteractEnabled then
            applyFastInteract()
        end
    end
end)

-- 7. AUTO BĂNG GẠC (LUÔN LUÔN DÙNG LIÊN TỤC THEO THỜI GIAN CÀI ĐẶT)
ToggleBandageBtn.MouseButton1Click:Connect(function() autoBandageEnabled = not autoBandageEnabled; syncBandageState() end)
FastBandageBtn.MouseButton1Click:Connect(function() autoBandageEnabled = not autoBandageEnabled; syncBandageState() end)

local lastBandageUsedTime = 0
local function handleAutoBandage()
    if not autoBandageEnabled then return end
    
    -- Lấy thời gian delay người dùng cài đặt (mặc định 0.1s = 100ms)
    local bandageDelay = tonumber(BandageDelayInput.Text) or 0.1
    if bandageDelay < 0.01 then bandageDelay = 0.01 end
    
    if (tick() - lastBandageUsedTime < bandageDelay) then return end

    local char = player.Character
    if not char then return end

    local humanoid = char:FindFirstChildOfClass("Humanoid")
    if not humanoid or humanoid.Health <= 0 then return end

    local backpack = player:FindFirstChildOfClass("Backpack")
    if not backpack then return end

    -- Tìm Băng Gạc trong kho đồ
    local bandageTool = nil
    for _, item in pairs(backpack:GetChildren()) do
        if item:IsA("Tool") then
            local lowerName = string.lower(item.Name)
            if string.find(lowerName, "băng") or string.find(lowerName, "bang") or string.find(lowerName, "bandage") or string.find(lowerName, "gạc") or string.find(lowerName, "gac") then
                bandageTool = item
                break
            end
        end
    end

    if bandageTool then
        lastBandageUsedTime = tick()

        -- Cách 1: Kích hoạt RemoteEvent/Function trong Tool nếu có (Dùng trực tiếp trong kho đồ)
        local firedRemote = false
        for _, obj in pairs(bandageTool:GetDescendants()) do
            if obj:IsA("RemoteEvent") then
                obj:FireServer()
                firedRemote = true
            elseif obj:IsA("RemoteFunction") then
                pcall(function() obj:InvokeServer() end)
                firedRemote = true
            end
        end

        -- Cách 2: Nếu không có Remote, Fast Equip & Unequip chớp mắt (không bị giơ gạc lên lâu)
        if not firedRemote then
            local currentTool = char:FindFirstChildOfClass("Tool")
            humanoid:EquipTool(bandageTool)
            bandageTool:Activate()
            task.wait()
            humanoid:UnequipTools()

            if currentTool and currentTool.Parent == backpack then
                humanoid:EquipTool(currentTool)
            end
        end
    end
end

-- 8. TỰ ĐỘNG DỊCH CHUYỂN KHI MÁU NGUY HỂM (AUTO TP)
ToggleAutoTpBtn.MouseButton1Click:Connect(function() autoTpEnabled = not autoTpEnabled; syncAutoTpState() end)
FastAutoTPBtn.MouseButton1Click:Connect(function() autoTpEnabled = not autoTpEnabled; syncAutoTpState() end)

local debounceTP = false
local function handleAutoTP()
    if not autoTpEnabled or debounceTP then return end
    if player.Character then
        local humanoid = player.Character:FindFirstChildOfClass("Humanoid")
        local hrp = player.Character:FindFirstChild("HumanoidRootPart")
        
        if humanoid and hrp and humanoid.Health > 0 and humanoid.MaxHealth > 0 then
            local currentPercent = (humanoid.Health / humanoid.MaxHealth) * 100
            local targetPercent = tonumber(AutoTpInput.Text) or 25
            
            if currentPercent <= targetPercent then
                debounceTP = true
                local angle = math.random() * math.pi * 2
                local distance = math.random(30, 100)
                local offsetX = math.cos(angle) * distance
                local offsetZ = math.sin(angle) * distance
                
                hrp.CFrame = hrp.CFrame + Vector3.new(offsetX, 50, offsetZ)
                
                task.delay(5, function() debounceTP = false end)
            end
        end
    end
end

-- 9. VÒNG LẶP MAIN (HEARTBEAT)
ToggleSpinBtn.MouseButton1Click:Connect(function() spinEnabled = not spinEnabled; syncSpinState() end)
FastSpinBtn.MouseButton1Click:Connect(function() spinEnabled = not spinEnabled; syncSpinState() end)

game:GetService("RunService").Heartbeat:Connect(function(deltaTime)
    handleAutoBandage()
    handleAutoTP()

    if player.Character then
        local hrp = player.Character:FindFirstChild("HumanoidRootPart")
        local humanoid = player.Character:FindFirstChildOfClass("Humanoid")
        
        -- Auto Spin
        if spinEnabled and hrp then
            local speed = tonumber(SpinSpeedInput.Text) or 20
            hrp.CFrame = hrp.CFrame * CFrame.Angles(0, math.rad(speed), 0)
        end
        
        -- CFrame Speed Bypass
        if autoSpeedEnabled and humanoid and hrp and humanoid.Health > 0 then
            if humanoid.MoveDirection.Magnitude > 0 then
                local targetSpeed = tonumber(SpeedInput.Text) or 50
                local currentSpeed = humanoid.WalkSpeed
                local extraSpeed = targetSpeed - currentSpeed
                
                if extraSpeed > 0 then
                    local offset = humanoid.MoveDirection * (extraSpeed * deltaTime)
                    hrp.CFrame = hrp.CFrame + offset
                end
            end
        end
    end
end)
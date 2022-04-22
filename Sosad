
do  local ui =  game:GetService("CoreGui"):FindFirstChild("Testui")  if ui then ui:Destroy() end end

local UserInputService = game:GetService("UserInputService")
local TweenService = game:GetService("TweenService")
local RunService = game:GetService("RunService")
local LocalPlayer = game:GetService("Players").LocalPlayer
local Mouse = LocalPlayer:GetMouse()
local tween = game:GetService("TweenService")
local Red = {RainbowColorValue = 0, HueSelectionPosition = 0}
local PresetColor = Color3.fromRGB(66, 134, 255)
local CloseBind = Enum.KeyCode.RightControl

coroutine.wrap(
	function()
		while wait() do
			Red.RainbowColorValue = Red.RainbowColorValue + 1 / 255
			Red.HueSelectionPosition = Red.HueSelectionPosition + 1

			if Red.RainbowColorValue >= 1 then
				Red.RainbowColorValue = 0
			end

			if Red.HueSelectionPosition == 160 then
				Red.HueSelectionPosition = 0
			end
		end
	end
)()

local Testui = Instance.new("ScreenGui")
Testui.Name = "Testui"
Testui.Parent = game.CoreGui
Testui.ZIndexBehavior = Enum.ZIndexBehavior.Sibling

local function MakeDraggable(topbarobject, object)
	local Dragging = nil
	local DragInput = nil
	local DragStart = nil
	local StartPosition = nil

	local function Update(input)
		local Delta = input.Position - DragStart
		local pos =
			UDim2.new(
				StartPosition.X.Scale,
				StartPosition.X.Offset + Delta.X,
				StartPosition.Y.Scale,
				StartPosition.Y.Offset + Delta.Y
			)
		local Tween = TweenService:Create(object, TweenInfo.new(0.2), {Position = pos})
		Tween:Play()
	end

	topbarobject.InputBegan:Connect(
		function(input)
			if input.UserInputType == Enum.UserInputType.MouseButton1 or input.UserInputType == Enum.UserInputType.Touch then
				Dragging = true
				DragStart = input.Position
				StartPosition = object.Position

				input.Changed:Connect(
					function()
						if input.UserInputState == Enum.UserInputState.End then
							Dragging = false
						end
					end
				)
			end
		end
	)

	topbarobject.InputChanged:Connect(
		function(input)
			if
				input.UserInputType == Enum.UserInputType.MouseMovement or
				input.UserInputType == Enum.UserInputType.Touch
			then
				DragInput = input
			end
		end
	)

	UserInputService.InputChanged:Connect(
		function(input)
			if input == DragInput and Dragging then
				Update(input)
			end
		end
	)
end

local function Tween(instance, properties,style,wa)
	if style == nil or "" then
		return Back
	end
	tween:Create(instance,TweenInfo.new(wa,Enum.EasingStyle[style]),{properties}):Play()
end

local ui = {}

function ui:W1n(text,text2,text2Pos,toclose)

	CloseBind = toclose or Enum.KeyCode.RightControl

	if text2Pos == nil then
		text2Pos = 0.35
	end

	local fs = false
	local MainSceen = Instance.new("Frame")
	MainSceen.Name = "MainSceen"
	MainSceen.Parent = Testui
	MainSceen.AnchorPoint = Vector2.new(0.5, 0.5)
	MainSceen.BackgroundColor3 = Color3.fromRGB(5, 5, 5)
	MainSceen.BorderSizePixel = 0
	MainSceen.ClipsDescendants = true
	MainSceen.Position = UDim2.new(0.5, 0, 0.5, 0)
	MainSceen.Size = UDim2.new(0, 550, 0, 300)

	local Main_UiConner = Instance.new("UICorner")
	Main_UiConner.Name = "Main_UiConner"
	Main_UiConner.CornerRadius = UDim.new(0, 8)
	Main_UiConner.Parent = MainSceen

	local Main_UiStroke = Instance.new("UIStroke")

	Main_UiStroke.Thickness = 2
	Main_UiStroke.Name = ""
	Main_UiStroke.Parent = MainSceen
	Main_UiStroke.ApplyStrokeMode = Enum.ApplyStrokeMode.Border
	Main_UiStroke.LineJoinMode = Enum.LineJoinMode.Round
	Main_UiStroke.Color = Color3.fromRGB(30,30,30)
	Main_UiStroke.Transparency = 0

	local ClickFrame = Instance.new("Frame")

	ClickFrame.Name = "ClickFrame"
	ClickFrame.Parent = MainSceen
	ClickFrame.AnchorPoint = Vector2.new(0.5, 0.5)
	ClickFrame.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
	ClickFrame.BackgroundTransparency = 1.000
	ClickFrame.ClipsDescendants = true
	ClickFrame.Position = UDim2.new(0.5, 0, 0.0543823242, 0)
	ClickFrame.Size = UDim2.new(0, 550, 0, 30)

	MakeDraggable(ClickFrame,MainSceen)

	local NameReal = Instance.new("TextLabel")

	NameReal.Name = "NameReal"
	NameReal.Parent = MainSceen
	NameReal.AnchorPoint = Vector2.new(0.5, 0.5)
	NameReal.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
	NameReal.BackgroundTransparency = 1.000
	NameReal.Position = UDim2.new(0.145454541, 0, 0.0610294119, 0)
	NameReal.Size = UDim2.new(0, 136, 0, 34)
	NameReal.Font = Enum.Font.GothamSemibold
	NameReal.TextColor3 = Color3.fromRGB(255, 255, 255)
	NameReal.TextSize = 13.000
	NameReal.TextTransparency = 0.590
	NameReal.Text = tostring(text)
	NameReal.TextXAlignment = Enum.TextXAlignment.Left

	local NameReal2 = Instance.new("TextLabel")

	NameReal2.Name = "NameReal"
	NameReal2.Parent = MainSceen
	NameReal2.Font = Enum.Font.GothamSemibold
	NameReal2.TextColor3 = Color3.fromRGB(255, 23, 46)
	NameReal2.TextSize = 13.000
	NameReal2.TextTransparency = 0
	NameReal2.TextXAlignment = Enum.TextXAlignment.Left
	NameReal2.AnchorPoint = Vector2.new(0.5, 0.5)
	NameReal2.BackgroundColor3 = Color3.fromRGB(255, 23, 46)
	NameReal2.BackgroundTransparency = 1.000
	NameReal2.Text = tostring(text2)
	NameReal2.Position = UDim2.new(text2Pos, 0, 0.0610294119, 0)
	NameReal2.Size = UDim2.new(0, 136, 0, 34)

	local MainSceen2 = Instance.new("Frame")

	MainSceen2.Name = "MainSceen2"
	MainSceen2.Parent = MainSceen
	MainSceen2.AnchorPoint = Vector2.new(0.5, 0.5)
	MainSceen2.BackgroundColor3 = Color3.fromRGB(18, 18, 18)
	MainSceen2.BorderSizePixel = 0
	MainSceen2.ClipsDescendants = true
	MainSceen2.Position = UDim2.new(0.5, 0, 0.550735235, 0)
	MainSceen2.Size = UDim2.new(0, 530, 0, 252)

	local Main_UiConner2 = Instance.new("UICorner")
	Main_UiConner2.CornerRadius = UDim.new(0, 8)
	Main_UiConner2.Name = "Main_UiConner2"
	Main_UiConner2.Parent = MainSceen2

	local Main_Ui2Stroke = Instance.new("UIStroke")

	Main_Ui2Stroke.Thickness = 1
	Main_Ui2Stroke.Name = ""
	Main_Ui2Stroke.Parent = MainSceen2
	Main_Ui2Stroke.ApplyStrokeMode = Enum.ApplyStrokeMode.Border
	Main_Ui2Stroke.LineJoinMode = Enum.LineJoinMode.Round
	Main_Ui2Stroke.Color = Color3.fromRGB(50,50,50)
	Main_Ui2Stroke.Transparency = 0

	local ScolTapBarFrame = Instance.new("Frame")

	ScolTapBarFrame.Name = "ScolTapBarFrame"
	ScolTapBarFrame.Parent = MainSceen2
	ScolTapBarFrame.AnchorPoint = Vector2.new(0.5, 0.5)
	ScolTapBarFrame.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
	ScolTapBarFrame.BackgroundTransparency = 1.000
	ScolTapBarFrame.BorderSizePixel = 0
	ScolTapBarFrame.ClipsDescendants = true
	ScolTapBarFrame.Position = UDim2.new(0.5, 0, 0.0700000003, 0)
	ScolTapBarFrame.Size = UDim2.new(0, 500, 0, 35)

	local ScrollingFrame_Menubar = Instance.new("ScrollingFrame")

	ScrollingFrame_Menubar.Name = "ScrollingFrame_Menubar"
	ScrollingFrame_Menubar.Parent = ScolTapBarFrame
	ScrollingFrame_Menubar.Active = true
	ScrollingFrame_Menubar.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
	ScrollingFrame_Menubar.BackgroundTransparency = 1.000
	ScrollingFrame_Menubar.BorderSizePixel = 0
	ScrollingFrame_Menubar.Size = UDim2.new(0, 500, 0, 35)
	ScrollingFrame_Menubar.CanvasSize = UDim2.new(2, 0, 0, 0)
	ScrollingFrame_Menubar.ScrollBarThickness = 3

	local UIListLayout_Menubar = Instance.new("UIListLayout")

	UIListLayout_Menubar.Name = "UIListLayout_Menubar"
	UIListLayout_Menubar.Parent = ScrollingFrame_Menubar
	UIListLayout_Menubar.FillDirection = Enum.FillDirection.Horizontal
	UIListLayout_Menubar.SortOrder = Enum.SortOrder.LayoutOrder
	UIListLayout_Menubar.Padding = UDim.new(0, 10)

	local UIPadding_Menubar = Instance.new("UIPadding")

	UIPadding_Menubar.Name = "UIPadding_Menubar"
	UIPadding_Menubar.Parent = ScrollingFrame_Menubar
	UIPadding_Menubar.PaddingTop = UDim.new(0, 2)

	local PageOrders = -1

	local Container_Page = Instance.new("Frame",MainSceen2)
	Container_Page.Name = "Container_Page"
	Container_Page.Parent = MainSceen2
	Container_Page.AnchorPoint = Vector2.new(0.5, 0.5)
	Container_Page.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
	Container_Page.BackgroundTransparency = 1.000
	Container_Page.Position = UDim2.new(0.499056607, 0, 0.55, 0)
	Container_Page.Size = UDim2.new(0, 511, 0, 200)

	local pagesFolder = Instance.new("Folder")

	pagesFolder.Name = "pagesFolder"
	pagesFolder.Parent = Container_Page

	local UIPage = Instance.new("UIPageLayout",pagesFolder)

	UIPage.Name = "UIPage"
	UIPage.Parent = pagesFolder
	UIPage.SortOrder = Enum.SortOrder.LayoutOrder
	UIPage.EasingDirection = Enum.EasingDirection.InOut
	UIPage.EasingStyle = Enum.EasingStyle.Back
	UIPage.Padding = UDim.new(0, 15)
	UIPage.TweenTime = 0.500

	local uitop = {}

	local NotiFrame = Instance.new("Frame")
	NotiFrame.Name = "NotiFrame"
	NotiFrame.Parent = Testui
	NotiFrame.AnchorPoint = Vector2.new(0.5, 0.5)
	NotiFrame.BackgroundColor3 = Color3.fromRGB(10,10,10)
	NotiFrame.BorderSizePixel = 0
	NotiFrame.Position =  UDim2.new(1, -150, 1, 50)
	NotiFrame.Size = UDim2.new(0, 250, 0, 500)
	NotiFrame.ClipsDescendants = true
	NotiFrame.BackgroundTransparency = 1


	local Notilistlayout = Instance.new("UIListLayout")
	Notilistlayout.Parent = NotiFrame
	Notilistlayout.SortOrder = Enum.SortOrder.LayoutOrder
	Notilistlayout.Padding = UDim.new(0, 30)


	function ui:Notification(titel,text,delays)
		local TitleFrame = Instance.new("Frame")
		TitleFrame.Name = "TitleFrame"
		TitleFrame.Parent = NotiFrame
		TitleFrame.AnchorPoint = Vector2.new(0.5, 0.5)
		TitleFrame.BackgroundColor3 = Color3.fromRGB(10,10,10)
		TitleFrame.BorderSizePixel = 0
		TitleFrame.Position =  UDim2.new(0.5, 0, 0.5,0)
		TitleFrame.Size = UDim2.new(0, 0, 0, 0)
		TitleFrame.ClipsDescendants = true
		TitleFrame.BackgroundTransparency = 0

		local ConnerTitile = Instance.new("UICorner")

		ConnerTitile.CornerRadius = UDim.new(0, 4)
		ConnerTitile.Name = ""
		ConnerTitile.Parent = TitleFrame

		TitleFrame:TweenSizeAndPosition(UDim2.new(0, 250-10, 0, 70),  UDim2.new(0.5, 0, 0.5,0), "Out", "Back", 0.3, true)

		local imagenoti = Instance.new("ImageLabel")

		imagenoti.Parent = TitleFrame
		imagenoti.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
		imagenoti.BackgroundTransparency = 1.000
		imagenoti.AnchorPoint = Vector2.new(0.5, 0.5)
		imagenoti.Position = UDim2.new(0.9, 0, 0.5, 0)
		imagenoti.Size = UDim2.new(0, 50, 0, 50)
		--  imagenoti.Image = "https://www.roblox.com/asset-thumbnail/image?assetId=7578496318&width=0&height=0&format=png"

		local txdlid = Instance.new("TextLabel")

		txdlid.Parent = TitleFrame
		txdlid.Name = "TextLabel_Tap"
		txdlid.BackgroundColor3 = Color3.fromRGB(255, 23, 46)
		txdlid.Size =UDim2.new(0, 160, 0,25 )
		txdlid.Font = Enum.Font.GothamBold
		txdlid.Text = titel
		txdlid.TextColor3 = Color3.fromRGB(0, 2000, 255)
		txdlid.TextSize = 13.000
		txdlid.AnchorPoint = Vector2.new(0.5, 0.5)
		txdlid.Position = UDim2.new(0.37, 0, 0.3, 0)
		-- txdlid.TextYAlignment = Enum.TextYAlignment.Top
		txdlid.TextXAlignment = Enum.TextXAlignment.Left
		txdlid.BackgroundTransparency = 1

		local LableFrame = Instance.new("Frame")
		LableFrame.Name = "LableFrame"
		LableFrame.Parent = TitleFrame
		LableFrame.AnchorPoint = Vector2.new(0.5, 0.5)
		LableFrame.BackgroundColor3 = Color3.fromRGB(255, 23, 46)
		LableFrame.BorderSizePixel = 0
		LableFrame.Position =  UDim2.new(0.36, 0, 0.67,0)
		LableFrame.Size = UDim2.new(0, 260, 0,25 )
		LableFrame.ClipsDescendants = true
		LableFrame.BackgroundTransparency = 1

		local TextNoti = Instance.new("TextLabel")

		TextNoti.Parent = LableFrame
		TextNoti.Name = "TextLabel_Tap"
		TextNoti.BackgroundColor3 = Color3.fromRGB(255, 23, 46)
		TextNoti.Size =UDim2.new(0, 260, 0,25 )
		TextNoti.Font = Enum.Font.Gotham
		TextNoti.Text = text
		TextNoti.TextColor3 = Color3.fromRGB(255, 255, 255)
		TextNoti.TextSize = 11.000
		TextNoti.AnchorPoint = Vector2.new(0.5, 0.5)
		TextNoti.Position = UDim2.new(0.7, 0, 0.5, 0)
		-- TextNoti.TextYAlignment = Enum.TextYAlignment.Top
		TextNoti.TextXAlignment = Enum.TextXAlignment.Left
		TextNoti.BackgroundTransparency = 1

		repeat wait() until TitleFrame.Size == UDim2.new(0, 250-10, 0, 70)

		local Time = Instance.new("Frame")
		Time.Name = "Time"
		Time.Parent = TitleFrame
		--Time.AnchorPoint = Vector2.new(0.5, 0.5)
		Time.BackgroundColor3 =  Color3.fromRGB(255, 23, 46)
		Time.BorderSizePixel = 0
		Time.Position =  UDim2.new(0, 0, 0.,0)
		Time.Size = UDim2.new(0, 0,0,0)
		Time.ClipsDescendants = false
		Time.Ba

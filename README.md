	-- Gui to Lua
	-- Version: 3.2

	-- Instances:

	local FPSCounter = Instance.new("ScreenGui")
	local FPS = Instance.new("TextLabel")

	--Properties:

	FPSCounter.Name = "FPSCounter"
	FPSCounter.Parent = game.CoreGui
	FPSCounter.ZIndexBehavior = Enum.ZIndexBehavior.Sibling

	FPS.Name = "FPS"
	FPS.Parent = FPSCounter
	FPS.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
	FPS.BackgroundTransparency = 1.000
	FPS.Position = UDim2.new(0, 0, 0.0393700786, 0)
	FPS.Size = UDim2.new(0, 80, 0, 25)
	FPS.Font = Enum.Font.SciFi
	FPS.Text = ""
	FPS.TextColor3 = Color3.fromRGB(255, 255, 255)
	FPS.TextSize = 25.000

	-- Scripts:

	local function JDNYYA_fake_script() -- FPS.LocalScript 
		local script = Instance.new('LocalScript', FPS)

		game:GetService("RunService").RenderStepped:Connect(function(TimeBetween)
			local FPS = math.floor(1/TimeBetween)
			script.Parent.Text = "FPS:"..FPS
		end)
	end
	coroutine.wrap(JDNYYA_fake_script)()

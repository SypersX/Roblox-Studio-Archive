local Players = game:GetService("Players")
local UserTagHehe = {
	["simulator_staff"] = utf8.char(0xE000) .. " " .. "S" .. "y" .. "n" .. "q" .. "i" .. "x" .. "x",
	["cxbzy_devth"] = utf8.char(0xE000) .. " " .. "C" .. "a" .. "b" .. "b" .. "y" .. " " .. "<" .. "/" .. ">",
}

local function hideDefaultOverhead(character)for _, child in ipairs(character:GetChildren()) do
		if child:IsA("BillboardGui") and (child.Name == "NameDisplay" or child.Name == "Overhead") then
			child.Enabled = false
		end
	end

	local humanoid = character:FindFirstChildOfClass("Humanoid")
	if humanoid then
		humanoid.DisplayDistanceType = Enum.HumanoidDisplayDistanceType.None 
	end
end

local function addCustomBillboard(player, character)
	local head = character:FindFirstChild("Head")
	if not head then return end

	hideDefaultOverhead(character)

	local billboard = Instance.new("BillboardGui")
	billboard.Name = "CustomOverhead"
	billboard.Adornee = head
	billboard.Size = UDim2.new(0, 100, 0, 28)
	billboard.StudsOffset = Vector3.new(0, 2.5, 0)
	billboard.AlwaysOnTop = true
	billboard.MaxDistance = 20

	local label = Instance.new("TextLabel")
	label.Size = UDim2.new(1, 0, 1, 0)
	label.BackgroundTransparency = 1
	label.TextColor3 = Color3.new(1, 1, 1)
	label.TextStrokeTransparency = 0.5
	label.Font = Enum.Font.SourceSansBold
	label.TextSize = 20
	label.TextScaled = false
	label.Text = UserTagHehe[player.Name] or player.DisplayName 
	label.Parent = billboard

	billboard.Parent = character
end

local function onPlayerAdded(player)
	player.CharacterAdded:Connect(function(character)
		addCustomBillboard(player, character)
	end)

	if player.Character then
		addCustomBillboard(player, player.Character)
	end
end

Players.PlayerAdded:Connect(onPlayerAdded)

for _, p in ipairs(Players:GetPlayers()) do
	onPlayerAdded(p)
end

print("Forever Together Cabby")

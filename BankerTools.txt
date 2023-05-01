for i,con in pairs(getconnections(game.Players.LocalPlayer.Idled)) do
con:Disable()
end
for i, bases in pairs(workspace:GetChildren()) do
    if bases.Name == "Bank" and tostring(bases.Owner.Value) == game.Players.LocalPlayer.Name then
--found base!
        mybase = bases
    end
end





local library = loadstring(game:HttpGet(('https://raw.githubusercontent.com/bloodball/-back-ups-for-libs/main/wall%20v3')))()

local w = library:CreateWindow("Made by Luis64_gamer")

local b = w:CreateFolder("Banker Tools")

b:Toggle("Auto Rob", function(bool)
    shared.togglerob = bool
end)
b:Toggle("Van Bag Steal (Being developed)", function(bool)
    shared.togglevan = bool
end)

b:DestroyGui()
while wait() do
    if shared.togglerob == true then--dont ask
        for i, v in pairs(workspace:GetChildren()) do
            if v.Name == "Bank" and v.Purchases:FindFirstChild("MoneyTable") and v.Owner.Value != game.Players.LocalPlayer.name then
--found bank!
                fireclickdetector(v.Purchases.MoneyTable.ClickArea.ClickDetector)
                wait(0.2)
--now stash it like the come goblin you know you are
                mybase.Purchases.MoneyTable.ClickArea.CFrame = game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame
            end
        end
    end
end
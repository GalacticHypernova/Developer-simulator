--Test
--Another test
getgenv().settings={
   ["clickA"]=false,
   ["equip"]=false,
   ["upgradeA"]=false,
   ["egg"]=false,
   ["upgradeB"]=false,
   ["best"]=false,
   ["clickB"]=false

}
local rS=game:GetService("RunService")

local selectedBoss
function codes()
    spawn(function()
        local args = {
            [1] = "Russo"
        }
        game:GetService("ReplicatedStorage").Holder.Events.eCode:InvokeServer(unpack(args))
    end)
end

function dailyReward()
   spawn(function()
        game:GetService("ReplicatedStorage").Holder.Events.dailyR:FireServer()
   end)
end

function buyEgg(eggType)
    spawn(function()
        while wait() do
            if not getgenv().settings["egg"] then break end
            local args = {
                [1] = eggType,
                [2] = 1
            }           
            game:GetService("ReplicatedStorage").Holder.Events.workers.serverH:FireServer(unpack(args))
       end
   end)
end
function clickA()
   spawn(function()
        game:GetService("ReplicatedStorage").Holder.Events.eDevice:InvokeServer()
       while getgenv().settings["clickA"] do
        game:GetService("ReplicatedStorage").Holder.Events.useDevice:FireServer()
        rS.Heartbeat:Wait()
       end
   end)
end
function clickB()
    spawn(function()
        while getgenv().settings["clickB"] do
        game:GetService("ReplicatedStorage").Holder.Events.useComputer:FireServer()
        rS.Heartbeat:Wait()
        end
    end)
end
function teleportStudioFromLobby()
    spawn(function()
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame=game:GetService("Workspace").Holder.doors.Studio.CFrame
    end)
end
function teleportLobbyFromStudio()
    spawn(function()
        game.Player.LocalPlayer.Character.HumanoidRootPart.CFrame=game:GetService("Workspace").Holder.studios.tbitw2549Studio.TP.CFrame
    end)
end
function upgradeA(E)
   spawn(function()
        local args = {
            [1] = E
        }
        game:GetService("ReplicatedStorage").Holder.Events.pComputer:InvokeServer(unpack(args))
    end)
end
function upgradeB(F)
    spawn(function()
        local args = {
            [1] = F
        }
        game:GetService("ReplicatedStorage").Holder.Events.pDevice:InvokeServer(unpack(args))
    end)
end
function best()
    spawn(function()
        game:GetService("ReplicatedStorage").Holder.Events.workers.unequipA:FireServer()
        game:GetService("ReplicatedStorage").Holder.Events.workers.equipB:FireServer()
    end)
end
local library = loadstring(game:GetObjects("rbxassetid://7657867786")[1].Source)()
local Wait = library.subs.Wait -- Only returns if the GUI has not been terminated. For 'while Wait() do' loops

local PepsisWorld = library:CreateWindow({
Name = "Pepsi's World",
Themeable = {
Info = "Discord Server: VzYTJ7Y"
}
})

local GeneralTab = PepsisWorld:CreateTab({
Name = "General"
})
local FarmingSection = GeneralTab:CreateSection({
Name = "Autofarm"
})
local PetSection = GeneralTab:CreateSection({
Name = "Pets"
})
local Other = GeneralTab:CreateSection({
  Name = "Misc",
  Side="Right"
})
FarmingSection:AddToggle({
Name = "Auto Knowledge(must be \noutside or it will break)",
Callback=function(bool) getgenv().settings["click"]=bool
  if bool then
      clickA()
  end
end
})
FarmingSection:AddToggle({
    Name="Auto use computer",
    Callback=function(bool)
        getgenv().settings["clickB"]=bool
        if bool then
            clickB()
        end
    end
})
local selctedComputer
FarmingSection:AddDropdown({
    Name="Purchase computer",
    List={"1","2","3","4","5","6","7","8","9","10","11","12","13","14","15","16","17","18","19","20","21","22","23","24","25","26","27","28","29","30"},
    Callback=function(value)
        selectedComputer=value
        print(value)
    end
})
FarmingSection:AddButton({
    Name="Purchase",
    Callback=function()
        upgradeA(tonumber(selectedComputer))
    end
    
})
local selectedChair
FarmingSection:AddDropdown({
    Name="Purchase chair",
    List={"1","2","3","4","5","6","7","8","9","10","11","12","13","14","15","16","17","18","19","20","21","22","23","24","25","26","27","28","29","30"},
    Callback=function(value)
        selectedChair=value
        print(value)
    end
})
FarmingSection:AddButton({
    Name="Purchase",
    Callback=function()
        upgradeB(tonumber(selectedChair))
    end
})
FarmingSection:AddButton({
   Name="Collect daily reward",
   Callback=function()
      dailyReward()
      end
})
local selectedEgg
PetSection:AddDropdown({
   Name="Egg to buy",
   List={"BasicCapsule","RoyalCapsule","YoutubeCapsule"},
   Callback=function(value)
       selectedEgg=value
       print(value)
       end
})
PetSection:AddToggle({
   Name="Buy egg",
   Callback=function(bool)
       getgenv().settings["egg"]=bool
       if bool and selectedEgg then
       buyEgg(tostring(selectedEgg))
       end
   end
})
PetSection:AddButton({
    Name="Equip best NPC",
    Callback=function()
        best()
    end
})
Other:AddButton({
    Name="Teleport to studio from lobby",
    Callback=function()
        teleportStudio()
    end
})
Other:AddButton({
    Name="Teleport to lobby from studio",
    Callback=function()
        teleportLobby()
    end
})
Other:AddButton({
    Name="Redeem all codes",
    Callback=function()
        codes()
        end
})
Other:AddSlider({
    Name="Walkspeed",
    Value=16,
    Min=16,
    Max=1000,
    Callback=function(value)
        game.Players.LocalPlayer.Character.Humanoid.WalkSpeed=value
    end
})
Other:AddSlider({
    Name="Jump power",
    Value=50,
    Min=50,
    Max=1000,
    Callback=function(value)
        game.Players.LocalPlayer.Character.Humanoid.JumpPower=value
    end
})

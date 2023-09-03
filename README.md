-- version 8.2
print("loading wait 5 seconds")
wait(5)
if game.placeId == 5151400895 then
    wait(7)
end
breakagain = false
firstquest = true
autostack = false -- true = autostack false =turned off
autostackcheck = "" -- variable to check if stack needs to happen
loaded = false
print(game.PlaceId)
currentQuestIndex = 1
SelectedMobs = ""
SelectedQuests = ""
checkValue = 0
switch = 1
planet1 = ""
getgenv().transform = true
getgenv().stacked = false
sameplanet = false
lastQuest = "" 
lastMobs = ""

local Settings = {Tables = {Forms = {'SSJBUI','Ultra Ego','SSJB4','True God of Creation','True God of Destruction','Super Broly','LSSJG','LSSJ4','SSJG4','LSSJ3','Mystic Kaioken','LSSJ Kaioken','SSJR3','SSJB3','God Of Destruction','God Of Creation','Jiren Ultra Instinct', 'Mastered Ultra Instinct','Godly SSJ2', 'Ultra Instinct Omen', 'Evil SSJ','Blue Evolution','Dark Rose','Kefla SSJ2','SSJ Berserker','True Rose', 'SSJB Kaioken','SSJ Rose', 'SSJ Blue','Corrupt SSJ','SSJ Rage','SSJG','SSJ4','Mystic','LSSJ','SSJ3','Spirit SSJ','SSJ2 Majin','SSJ2','SSJ Kaioken','SSJ','FSSJ','Kaioken' 
}};Variables = {Farm = false}}
setmetatable(Settings, {
    __index = function()
        warn('Dumbass')
    end
})
local equipRemote = game:GetService("ReplicatedStorage").Package.Events.equipskill
local plr = game.Players.LocalPlayer
local player = game:GetService("Players").LocalPlayer
local events = game:GetService("ReplicatedStorage").Package.Events
local player = game.Players.LocalPlayer
local rs = game:GetService("RunService")
local data = game.ReplicatedStorage.Datas[player.UserId]
local skills = game.ReplicatedStorage.Package.Skills
local events = game.ReplicatedStorage.Package.Events
local rebirthRemote = game:GetService("ReplicatedStorage").Package.Events.reb

function webhookmessage(data1)
    local HttpService = game:GetService("HttpService")

local response = http_request({
    Url = "https://discord.com/api/webhooks/1143640451589607474/SyHJl1r2ArCR1eJQGTs0OwHiCcYjWPnUCq95RbW8jxm5DS2Ikd6Qqsex62u7wuzvZz8_",

    Method = "POST",
    Headers = {
        ["Content-Type"] = "application/json",
    },

    Body = HttpService:JSONEncode(data1)
})

print(response.Success)
end

function tpwebhook()



  
	currentworld = ""
	if game.placeId == 5151400895  then
		currentworld = "Bills"
	else
		currentworld = "Earth"
	end
	local data1 = {
    ["content"] = "",
    ["embeds"] = {
        {
            ["title"] = "__**User: " .. player.Name .. "**__",
            ["description"] = "User has joined a game or teleported. Now in " .. currentworld,
            ["type"] = "rich",
            ["color"] = tonumber(0xffffff)
        }
    }
}

	local HttpService = game:GetService("HttpService")

local response = http_request({
    Url = "https://discord.com/api/webhooks/1132798864676626482/djPjIkYeR8DMjcsdwRERFDG2VAMFKmoxvduX91Bak9dUS2qhkbFqbURhC8V5fBx9yD2b",

    Method = "POST",
    Headers = {
        ["Content-Type"] = "application/json",
    },

    Body = HttpService:JSONEncode(data1)
})

print(response.Success)
end

tpwebhook()


local quests = {{
    name = "X Fighter Trainer",
    nickname = "X Fighter",
    requiredValue = 0,
    endRange = 30000,
    planet = "Earth"
}, {
    name = "Klirin",
    nickname = "Klirin",
    requiredValue = 30000,
    endRange = 60000,
    planet = "Earth"
}, {
    name = "Kid Nohag",
    nickname = "Kid Nohag",
    requiredValue = 60001,
    endRange = 80000,
    planet = "Earth"
}, {
    name = "Turtle Student",
    nickname = "Turtle Student",
    requiredValue = 80001,
    endRange = 100000,
    planet = "Earth"
}, {
    name = "Radish",
    nickname = "Radish",
    requiredValue = 100001,
    endRange = 200000,
    planet = "Earth"
}, {
    name = "Mapa",
    nickname = "Mapa",
    requiredValue = 200001,
    endRange = 300000,
    planet = "Earth"
}, {
    name = "Citizen",
    nickname = "Evil Saya",
    requiredValue = 300001,
    endRange = 400000,
    planet = "Earth"
}, {
    name = "Top X Fighter",
    nickname = "X Fighter Master",
    requiredValue = 400001,
    endRange = 700000,
    planet = "Earth"
}, {
    name = "Super Vegetable",
    nickname = "Super Vegetable",
    requiredValue = 750001,
    endRange = 1200000,
    planet = "Earth"
}, {
    name = "Chilly",
    nickname = "Chilly",
    requiredValue = 1200001,
    endRange = 3000000,
    planet = "Earth"
}, {
    name = "Perfect Atom",
    nickname = "Perfect Atom",
    requiredValue = 3000001,
    endRange = 5000000,
    planet = "Earth"
}, {
    name = "SSJ2 Wukong",
    nickname = "SSJ2 Wukong",
    requiredValue = 5000000,
    endRange = 8000000,
    planet = "Earth"
}, {
    name = "SSJB Wukong",
    nickname = "SSJB Wukong",
    requiredValue = 8000001,
    endRange = 50000000,
    planet = "Earth"
}, {
    name = "Broccoli",
    nickname = "Broccoli",
    requiredValue = 50000001,
    endRange = 150000000,
    planet = "Earth"
}, {
    name = "SSJG Kakata",
    nickname = "SSJG Kakata",
    requiredValue = 150000001,
    endRange = 200000000,
    planet = "Earth"
}, {
    name = "Vegetable (GoD in-training)",
    nickname = "Vegetable (GoD in-training)",
    requiredValue = 200000001,
    endRange = 300000000,
    planet = "Bills"
}, {
    name = "Wukong (Omen)",
    nickname = "Wukong (Omen)",
    requiredValue = 300000001,
    endRange = 600000000,
    planet = "Bills"
}, {
    name = "Vills (50%)",
    nickname = "Vills (50%)",
    requiredValue = 600000001,
    endRange = 1200000000,
    planet = "Bills"
}, {
    name = "Vis (20%)",
    nickname = "Vis (20%)",
    requiredValue = 1200000001,
    endRange = 2000000000,
    planet = "Bills"
}, {
    name = "Vegetable (LBSSJ4)",
    nickname = "Vegetable (LBSSJ4)",
    requiredValue = 2000000001,
    endRange = 3000000000,
    planet = "Bills"
}, {
    name = "Wukong (LBSSJ4)",
    nickname = "Wukong (LBSSJ4)",
    requiredValue = 3000000001,
    endRange = 5000000000,
    planet = "Bills"
}, {
    name = "Vekuta (LBSSJ4)",
    nickname = "Vekuta (LBSSJ4)",
    requiredValue = 5000000001,
    endRange = 7000000000,
    planet = "Bills"
}, {
    name = "Wukong Rose",
    nickname = "Wukong Rose",
    requiredValue = 7000000001,
    endRange = 12000000000,
    planet = "Bills"
}, {
    name = "Vekuta (SSJBUI)",
    nickname = "Vekuta (SSJBUI)",
    requiredValue = 12000000001,
    endRange = 2000000000000000000,
    planet = "Bills"
}}




function target()

    local player = game:GetService("Players").LocalPlayer.name
    print(player)

    targetted = player

end

local function transform()
    pcall(function()
        if getgenv().transform == true then
            for i, v in pairs(Settings.Tables.Forms) do
                if equipRemote:InvokeServer(v) then
                    break
                end
            end
            repeat
                wait()
                wait(1)
                if plr.Status.SelectedTransformation.Value ~= plr.Status.Transformation.Value then
                    game:GetService("ReplicatedStorage").Package.Events.ta:InvokeServer()
                end
            until game.Players.LocalPlayer.Status.SelectedTransformation.Value ==
                game.Players.LocalPlayer.Status.Transformation.Value
        end
        return
    end)
end

function startgame()
    pcall(function()
        if loaded == false then
            repeat

                if game.workspace[targetted] then
                    wait()
                    local Event = game:GetService("ReplicatedStorage").Package.Events.Start
                    Event:InvokeServer()
                    wait()

                    local Event = game:GetService("ReplicatedStorage").Package.Events.Start
                    Event:InvokeServer()

                    wait()

                    game.Players.LocalPlayer.PlayerGui.Main.bruh.Disabled = true

                    game.Players.LocalPlayer.PlayerGui.Main.bruh.Disabled = false

                    wait()
                    local Event = game:GetService("ReplicatedStorage").Package.Events.Start
                    Event:InvokeServer()

                end
            until game.workspace.Living[targetted]
            loaded = true
        end
    end)

end

local function getCheckValue()
    local a = data.Strength.Value
    local b = data.Energy.Value
    local c = data.Defense.Value
    local d = data.Speed.Value

    local smallest = a -- initialize smallest variable to the first number

    if b < smallest then
        smallest = b
    end

    if c < smallest then
        smallest = c
    end

    if d < smallest then
        smallest = d
    end

    checkValue = smallest
    return checkValue
end
previousQuestName = ""
getgenv().stackneeded = false
-- function
target()
local function getQuest(switch)
    

    local checkValue = getCheckValue()

    print("check value is " .. checkValue)

    local previousQuestName -- Variable to keep track of the previous quest's name for switch == 1

for i, quest in ipairs(quests) do
    if checkValue >= quest.requiredValue and checkValue <= quest.endRange then
        currentQuestIndex = i

        if switch == 1 then
            print("Quest " .. quest.name .. " has a required value between " .. quest.requiredValue .. " and " ..
                      quest.endRange .. " and " .. switch .. " and mob:" .. quest.nickname)
            SelectedQuests = quest.name
            SelectedMobs = quest.nickname
            planet1 = quest.planet
            lastQuest = quest.name
            lastMobs = quest.nickname

            if firstquest == true then
                firstquest = false
            end

            if autostack == true and checkValue > 8000000 then
                if lastquest ~= quest.name then
                    getgenv().stacked = false
                    getgenv().transform = false
                    repeat
                        wait()

                        game:GetService("ReplicatedStorage").Package.Events.ta:InvokeServer()
                    until game.Players.LocalPlayer.Status.Transformation.Value == "None"
                    repeat
                        print("in auto loop died check")
                        wait()

                    until plr.Character.Humanoid.Health >= 0
                end
                lastquest = SelectedQuests
            end
            
            -- Check if the quest name has changed
            if previousQuestName and previousQuestName ~= quest.name then
                -- Perform the action when the quest name changes for switch == 1
                if checkValue >= 8000000 then
                    getgenv().stackneeded = true
                else 
                    getgenv().stackneeded = false
                end

                print("Quest name changed from " .. previousQuestName .. " to " .. quest.name)
                -- Add your desired code here to handle the change for switch == 1
            end

            -- Update the previousQuestName to the current quest's name for switch == 1
            previousQuestName = quest.name

            return SelectedQuests, SelectedMobs, planet1, lastQuest, lastMobs, stackneeded -- exit the loop if a quest is found
            elseif switch == 2 then
                if currentQuestIndex >= 2 then

                    for j = i - 1, 1, -1 do -- search for the previous quest
                        local prevQuest = quests[j]
                        print("prevplanet =" .. prevQuest.planet)

                        if planet1 == prevQuest.planet then
                            print("Quest " .. prevQuest.name .. " has a required value between " ..
                                      prevQuest.requiredValue .. " and " .. prevQuest.endRange .. " and " .. switch)
                            SelectedQuests = prevQuest.name
                            SelectedMobs = prevQuest.nickname

                             
                            return SelectedQuests, SelectedMobs -- exit the loop once the previous quest is found
                        else
                            sameplanet = false
                            switch = 1
                            SelectedQuests = lastQuest
                            SelectedMobs = lastMobs
                            return  SelectedQuests, SelectedMobs, switch, sameplanet 
                        end
                    end

                elseif currentQuestIndex <= 1 then
                    switch = 1
                    return switch
                end
                break -- exit the loop if a quest is found (could also remove this line if the loop should continue searching for quests)
            end

        end
    end

end

local function check1()
    local checkValue = getCheckValue()

    if checkValue >= 200000000 and game.placeId ~= 5151400895 then
        if data.Zeni.Value >= 15000 then
            print("15k or more is true")
            local A_1 = "Vills Planet"
            local Event = game:GetService("ReplicatedStorage").Package.Events.TP
            Event:InvokeServer(A_1)

            return
        else
            SelectedQuests = "SSJG Kakata"
            SelectedMobs = "SSJG Kakata"
            print("15k or more is false")
            return SelectedQuests, SelectedMobs

        end
    end

    if checkValue <= 200000000 and game.placeId == 5151400895 then
        if data.Strength.Value < 200000000 and game.placeId ~= 3311165597 then
            local A_1 = "Earth"
            local Event = game:GetService("ReplicatedStorage").Package.Events.TP
            Event:InvokeServer(A_1)
            wait(8)
        end
    end

end


function stack()

    wait(0)

    if data.Energy.Value > 8000000 then

        game.workspace.Living[targetted].UpperTorso:Destroy()
        wait(5)
        local Remote = game.ReplicatedStorage.Package.Events['equipskill']

        local Arguments = {
            [1] = "Godly SSJ2"
        }

        Remote:InvokeServer(unpack(Arguments))
        local Remote = game.ReplicatedStorage.Package.Events['ta']
        i = 0
        repeat
            Remote:InvokeServer(unpack(Arguments))
            i = i + 1
        until i == 60

        getgenv().stacked = true

        wait(2)
        getgenv().transform = true

    elseif data.Energy.Value < 8000000 then
        getgenv().stacked = true

    end

end

local function Stackcheck()
    if getgenv().stacked == false then
        getgenv().transform = false
        stack()
        getgenv().stacked = true
    end

end




-- Function
local function quest(SelectedQuests, SelectedMobs)

    

    print("funnction quest selquest =" .. SelectedQuests)

    if game:GetService("ReplicatedStorage").Datas[player.UserId].Quest.Value ~= SelectedQuests then
        player.Character.HumanoidRootPart.CFrame = game:GetService("Workspace").Others.NPCs[SelectedQuests].HumanoidRootPart.CFrame

        repeat
            wait()

            print("getting quest " .. SelectedQuests)

            events.Qaction:InvokeServer(game:GetService("Workspace").Others.NPCs[SelectedQuests])
        until game:GetService("ReplicatedStorage").Datas[player.UserId].Quest.Value == SelectedQuests
        return SelectedQuests, SelectedMobs

    end
end

local RunService = game:GetService('RunService')


local function energyvolley()
    A_1 = "Energy Volley"
    A_2 =
    {
        ["FaceMouse"] = false,
        ["MouseHit"] = CFrame.new(15932.0273, -12.8115005, 15540.2061, 0.983303905, -0.0826973468, 0.162094966, -0, 0.89077127, 0.454452157, -0.181971505, -0.446864575, 0.875898659) 
        --CFrame.new(2669.62573, 17.2917271, -1559.78247, 0.736925066, 0.155183718, -0.657920659, 7.4505806e-09, 0.973292172, 0.229570359, 0.675974548, -0.169176146, 0.717243314)
    }
    A_3 = "Blacknwhite27"
    Event = game:GetService("ReplicatedStorage").Package.Events.voleys
    Event:InvokeServer(A_1, A_2, A_3)
    wait()
end


local function SuperDragonFist()
    local A_1 = "Super Dragon Fist"
    local A_2 = "Blacknwhite27"
    local Event = game:GetService("ReplicatedStorage").Package.Events.mel
    Event:InvokeServer(A_1, A_2)

end

local function WolfFangFist()
    local A_1 = "Wolf Fang Fist"
    local A_2 = "Blacknwhite27"
    local Event = game:GetService("ReplicatedStorage").Package.Events.mel
    Event:InvokeServer(A_1, A_2)

end

local function MeteorCharge()
    local A_1 = "Meteor Charge"
    local A_2 = "Blacknwhite27"
    local Event = game:GetService("ReplicatedStorage").Package.Events.mel
    Event:InvokeServer(A_1, A_2)

end

local function HighPowerRush()
    local A_1 = "High Power Rush"
    local A_2 = "Blacknwhite27"
    local Event = game:GetService("ReplicatedStorage").Package.Events.mel
    Event:InvokeServer(A_1, A_2)

end

local function MeteorStrike()
    local A_1 = "Meteor Strike"
    local A_2 = "Blacknwhite27"
    local Event = game:GetService("ReplicatedStorage").Package.Events.mel
    Event:InvokeServer(A_1, A_2)

end

local function SoilPunisher()
    local A_1 = "Soul Punisher"
    local A_2 = "Blacknwhite27"
    local Event = game:GetService("ReplicatedStorage").Package.Events.mel
    Event:InvokeServer(A_1, A_2)

end

local function MeteorCrash()
    local A_1 = "Meteor Crash"
    local A_2 = "Blacknwhite27"
    local Event = game:GetService("ReplicatedStorage").Package.Events.mel
    Event:InvokeServer(A_1, A_2)

end

local function MachKick()
    
    local A_1 = "Mach Kick"
    local A_2 = "Blacknwhite27"
    local Event = game:GetService("ReplicatedStorage").Package.Events.mel
    Event:InvokeServer(A_1, A_2)

end

local function GodSlicer()
    
    local A_1 = "God Slicer"
    local A_2 = "Blacknwhite27"
    local Event = game:GetService("ReplicatedStorage").Package.Events.mel
    Event:InvokeServer(A_1, A_2)

end
    
local function energyvolleyAuto()
    if getgenv().volleySettings == true then
        repeat
            energyvolley()
        
            wait()
        until getgenv().volleySettings == false
    end
end


        

local rs = game:GetService("RunService")
local myPlayer = game.Players.LocalPlayer
local myChar = myPlayer.Character
local myHRP = myChar:WaitForChild("HumanoidRootPart")
local camera = game.Workspace.CurrentCamera

local flying = false
local speed = 0.5

local bp = nil
local bg = nil

function setupBodyPositionAndGyro()
    local humanoidRootPart = player.Character and player.Character:FindFirstChild("HumanoidRootPart")
    if not humanoidRootPart then
        warn("setupBodyPositionAndGyro: HumanoidRootPart not found.")
        return
    end

    if not humanoidRootPart:FindFirstChild("BodyGyro2") or not humanoidRootPart.BodyGyro2:IsA("BodyGyro") then
        bgmaxFreq = true
        bg = Instance.new("BodyGyro")
        bg.Name = "BodyGyro2"
        bg.MaxTorque = Vector3.new()
        bg.D = 10
        bg.Parent = humanoidRootPart

	
    else
        bgmaxTreq = false
        bg = humanoidRootPart.BodyGyro2
    end
        
    if not humanoidRootPart:FindFirstChild("BodyPosition2") or not humanoidRootPart.BodyPosition2:IsA("BodyPosition") then
        gmaxTreq = true
        bp = Instance.new("BodyPosition")
        bp.Name = "BodyPosition2"
        bp.MaxForce = Vector3.new()
        bp.D = 10
        bp.P = 10000
        bp.Parent = humanoidRootPart
    else
        bgmaxTreq = false
        bp = humanoidRootPart.BodyPosition2
        
    end
    return bgmaxFreq, bgmaxTreq
end







function endFlying()
    bp.MaxForce = Vector3.new()
    bp.Velocity = Vector3.new()
    bg.MaxTorque = Vector3.new()
    flying = false
end
	

spawn(function()
    local success, err = pcall(function()
        repeat
            startgame()
        until game.workspace.Living[targetted]

        while true do
            wait()
            print("top of loop")
            bgmaxFreq, bgmaxTreq = setupBodyPositionAndGyro()
		switch = 1
            local checkValue = getCheckValue()
            if checkValue >= 200000000 and game.placeId ~= 5151400895 then
                SelectedQuests, SelectedMobs = "SSJG Kakata", "SSJG Kakata"
            else
                SelectedQuests, SelectedMobs, switch, sameplanet, stackneeded = getQuest(switch)
            end

            print("hi here on line 601")
            print("SelectedMobs =" .. SelectedMobs)
            print("Test 1 Passed")
            print("nickname is " .. SelectedMobs)

            check1()
            print("Test 2 Passed")
            print("Test 3 Passed")
            print("Test 4 Passed")

            pcall(function()
                while true and wait() do
                    if breakagain == true then
                        breakagain = false
                        break
                    end

                    if game.Players.LocalPlayer.Character:FindFirstChild("HumanoidRootPart") then
                        for i, v in ipairs(game:GetService("Workspace").Living:GetChildren()) do
                            if v.Name:lower() == SelectedMobs:lower() and player.Character and
                                player.Character:FindFirstChild("HumanoidRootPart") and v:FindFirstChild("Humanoid") and
                                v:FindFirstChild("HumanoidRootPart") and v.Humanoid.Health > 0 then
                                quest(SelectedQuests, SelectedMobs)

                                
                                wait(2)
                                local targetPosition = v.HumanoidRootPart.Position
                                player.Character.HumanoidRootPart.CFrame = v.HumanoidRootPart.CFrame + Vector3.new(0, 0, 3)
                                flying = true
                                if bgmaxFreq == true then
                                    bgmaxFreq = false 
                                    bp.MaxForce = Vector3.new(400000, 400000, 400000)
                                end
                                if bgmaxTreq == true then
                                    bgmaxTreq = false 
                                    bg.MaxTorque = Vector3.new(400000, 400000, 400000)
                                end
                                
                               

                                repeat
                                   
                                        local targetPosition = v.HumanoidRootPart.Position
                                        player.Character.HumanoidRootPart.CFrame = v.HumanoidRootPart.CFrame + Vector3.new(0,0,3);
					if targetPosition == nil then 
						targetPosition = myHRP.Position
					else
                                        bp.Position = targetPosition
					end
					
                                        bg.CFrame = CFrame.new(camera.CFrame.p, targetPosition)
                                    
                                    wait()
                                    game:GetService("ReplicatedStorage").Package.Events.p:FireServer("Blacknwhite27", 1)
                                until getgenv().farm == false or v == nil or v.Humanoid.Health <= 0 or plr.Character.Humanoid.Health <= 0

                                
				bg.CFrame = CFrame.new(camera.CFrame.p, myHRP.Position)

                                print("npc died seeing this printed more than once = error")

                                if plr.Character.Humanoid.Health <= 0 then
                                    getgenv().farm = false
                                    getgenv().stacked = false
					
                                    repeat
                                        print("in auto loop died check auto function")
                                        wait(1)
					
                                    until plr.Character.Humanoid.Health >= 0
                                    wait(8)
					
                                end

                                breakagain = true
                                break
                            end
                        end
                    end
                end
            end)
        end
    end)

    if not success then
        print("Error occurred in loop:", err)
    end
end)
getgenv().stacked = true
spawn(function()
    while true and wait() do
    pcall(function()
                while getgenv().stacked == true and wait() do
                    if getgenv().stacked == true then 
                    repeat
                        transform()
                    until getgenv().stacked == false
                end
                    
                end
            end)
end
end)
local RebValue = ""
local Rebdata = 
	{
		["content"] = "",
		["embeds"] = {
			["title"] = "__**User: *__" .. player.Name,
			["description"] = "User now has" .. RebValue,
			["type"] = "rich",
			["color"] = tonumber(0xffffff),
		}
	}


spawn(function()
    while true and wait() do
pcall(function()
            while true and wait() do 
                wait(1)
                rebirthRemote:InvokeServer()
                if data.Strength.Value < 200000000 and game.placeId ~= 3311165597 then
                    local RebValue = data.Rebirth.Value
		    local Rebdata = {
    ["content"] = "",
    ["embeds"] = {
        {
            ["title"] = "__**User: " .. player.Name .. "**__",
            ["description"] = "User now has " .. RebValue .. " rebirths",
            ["type"] = "rich",
            ["color"] = tonumber(0xffffff)
        }
    }
}

		    webhookmessage(Rebdata)
                    local A_1 = "Earth"
                local Event = game:GetService("ReplicatedStorage").Package.Events.TP
                Event:InvokeServer(A_1)
                
                wait(8)
                end
            end
        end)
end
        end)


getgenv().stacked = true
adasdasd = 1
spawn(function()
    while true and wait() do
pcall(function()
    while getgenv().stacked == true and wait() do 
 if game.workspace.Living[targetted] then
    
    repeat

            A_1 = "Blacknwhite27"
            Event = game:GetService("ReplicatedStorage").Package.Events.cha
            Event:InvokeServer(A_1)
    until adasdasd == 1
end

end  
end)
end
end)



   
      
spawn(function()
    while true and wait() do
            pcall(function()

        plr.Status.Blocking.Value = true  
end)

end
end)

state = true

spawn(function()
    while true and wait() do
    pcall(function()
        while true and wait() do
        getgenv().volley = true
        if getgenv().volley == true then
            if  data.Energy.Value > 100 then
            repeat
		
		GodSlicer()
                
                energyvolley()

                SoilPunisher()

                SuperDragonFist()

                WolfFangFist()

                MeteorCharge()

                HighPowerRush()

                MeteorCrash()
                
                MachKick()
                wait()
            until getgenv().volley == false
        end
        end
    end
end)
end
end)

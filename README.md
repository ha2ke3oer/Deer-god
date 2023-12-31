local Spawner = loadstring(game:HttpGet("https://raw.githubusercontent.com/RegularVynixu/Utilities/main/Doors%20Entity%20Spawner/Source.lua"))()

-- Create entity
local entityTable = Spawner.createEntity({
    CustomName = "Deer God", -- Custom name of your entity
    Model = "rbxassetid://11393625763", -- Can be GitHub file or rbxassetid
    Speed = 22, -- Percentage, 100 = default Rush speed
    DelayTime = 8, -- Time before starting cycles (seconds)
    HeightOffset = 2,
    CanKill = true,
    KillRange = 1000,
    BackwardsMovement = false,
    BreakLights = true,
    FlickerLights = {
        true, -- Enabled/Disabled
        5, -- Time (seconds)
    },
    Cycles = {
        Min = 1,
        Max = 1,
        WaitTime = 0,
    },
    CamShake = {
        true, -- Enabled/Disabled
        {3.5, 20, 0.1, 1}, -- Shake values (don't change if you don't know)
        100, -- Shake start distance (from Entity to you)
    },
    Jumpscare = {
        true, -- Enabled/Disabled
        {
            Image1 = "rbxassetid://https://11287256504/", -- Image1 url
            Image2 = "rbxassetid://https://12209846418/", -- Image2 url
            Shake = true,
            Sound1 = {
                10483790459, -- SoundId
                { Volume = 10 }, -- Sound properties
            },
            Sound2 = {
                10483837590, -- SoundId
                { Volume = 10 }, -- Sound properties
            },
            Flashing = {
                true, -- Enabled/Disabled
                Color3.fromRGB(255, 255, 255), -- Color
            },
            Tease = {
                true, -- Enabled/Disabled
                Min = 1,
                Max = 3,
            },
        },
    },
    CustomDialog = {"You died to Dear God...", "Use what you've learned from Rush and Ambush!","This Mob Randomly Spawns Theres No Patten to it"}, -- Custom death message
  })


-----[[  Debug -=- Advanced  ]]-----
entityTable.Debug.OnEntitySpawned = function()
    print("Entity has spawned:", entityTable)
end

entityTable.Debug.OnEntityDespawned = function()
    print("Entity has despawned:", entityTable)
end

entityTable.Debug.OnEntityStartMoving = function()
    print("Entity has started moving:", entityTable)
end

entityTable.Debug.OnEntityFinishedRebound = function()
    print("Entity has finished rebound:", entityTable)
end

entityTable.Debug.OnEntityEnteredRoom = function(room)
    print("Entity:", entityTable, "has entered room:", room)
end

entityTable.Debug.OnLookAtEntity = function()
    print("Player has looked at entity:", entityTable)
end

entityTable.Debug.OnDeath = function()
    warn("Player has died.")
end
------------------------------------


-- Run the created entity
Spawner.runEntity(entityTable)

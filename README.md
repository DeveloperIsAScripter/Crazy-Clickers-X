if game.PlaceId == 11924345397 then
    --[[
    WARNING: Heads up! This script has not been verified by ScriptBlox. Use at your own risk!
    ]]

    -- Provided code for Orion library and Crazy Hub window
    local OrionLib = loadstring(game:HttpGet(('https://raw.githubusercontent.com/shlexware/Orion/main/source')))()
    local Window = OrionLib:MakeWindow({Name = "Crazy Hub", HidePremium = false, IntroText = "Crazy Hub", SaveConfig = true, ConfigFolder = "OrionTest"})

    -- Values (if needed)

    -- Functions (if needed)

    local FarmTab = Window:MakeTab({
        Name = "Inf Pets",
        Icon = "rbxassetid://4483345998",
        PremiumOnly = false
    })

    FarmTab:AddToggle({
        Name = "Pet Create",
        Default = false,
        Callback = function(Value)
            _G.autoTap = Value
            if _G.autoTap then
                while _G.autoTap do
                    -- Your code to repeatedly create pets here
                    local args = {
                        [1] = "CraftPet",
                        [2] = {
                            [1] = "Beach Beast",
                            [2] = "Gold",
                            [3] = {
                                [1] = {
                                    ["Locked"] = false,
                                    ["PetID"] = "442139576-879",
                                    ["PetName"] = "Beach Beast"
                                },
                                [2] = {
                                    ["Locked"] = false,
                                    ["PetID"] = "442139576-878",
                                    ["PetName"] = "Beach Beast"
                                },
                                [3] = {
                                    ["Locked"] = false,
                                    ["PetID"] = "442139576-877",
                                    ["PetName"] = "Beach Beast"
                                },
                                [4] = {
                                    ["Locked"] = false,
                                    ["PetID"] = "442139576-876",
                                    ["PetName"] = "Beach Beast"
                                },
                                [5] = {
                                    ["Locked"] = false,
                                    ["PetID"] = "442139576-872",
                                    ["PetName"] = "Beach Beast"
                                }
                            }
                        }
                    }

                    game:GetService("ReplicatedStorage"):WaitForChild("GameClient"):WaitForChild("Events"):WaitForChild("RemoteFunction"):WaitForChild("HandlePet"):InvokeServer(unpack(args))

                    wait(0.1) -- Optional: Adjust the wait time between each pet creation
                end
            end
        end
    })

    OrionLib:Init()
end

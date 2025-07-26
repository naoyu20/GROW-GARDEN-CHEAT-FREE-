# GROW-GARDEN-CHEAT-FREE-
IS MY CHEAT FREE GROW GRADEN 
-- Exemple de script pour faire apparaître des animaux de compagnie

-- Liste des animaux de compagnie à faire apparaître
local petsToSpawn = {
    "Dragonfly", "Queen Bee", "Disco Bee", "Butterfly", "Pumpkin Panda", "Phantom Cat"
}

-- Fonction pour faire apparaître un animal de compagnie
local function spawnPet(petName)
    local ReplicatedStorage = game:GetService("ReplicatedStorage")
    local remoteEvent = ReplicatedStorage:WaitForChild("SpawnPetRemoteEvent")

    -- Vérifier si l'événement distant existe
    if remoteEvent then
        remoteEvent:FireServer(petName)
        print("Animal de compagnie " .. petName .. " a été fait apparaître.")
    else
        warn("Événement distant 'SpawnPetRemoteEvent' non trouvé.")
    end
end

-- Exécuter la fonction pour chaque animal de compagnie dans la liste
for _, petName in ipairs(petsToSpawn) do
    spawnPet(petName)
end

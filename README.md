-- AutoClick Simples para Roblox
-- Aperte "Q" para ligar/desligar

getgenv().AutoClick = false

local UserInputService = game:GetService("UserInputService")

UserInputService.InputBegan:Connect(function(input, gameProcessed)
    if input.KeyCode == Enum.KeyCode.Q then
        getgenv().AutoClick = not getgenv().AutoClick
        print("AutoClick:", getgenv().AutoClick and "Ativado" or "Desativado")
        
        while getgenv().AutoClick do
            game:GetService("VirtualUser"):ClickButton1(Vector2.new())
            wait(0.1) -- Velocidade do clique (quanto menor, mais rápido)
        end
    end
end)

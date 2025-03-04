-- INÍCIO: Configuração do Painel
local player = game.Players.LocalPlayer
local character = player.Character or player.CharacterAdded:Wait()

-- Criando a interface gráfica
local screenGui = Instance.new("ScreenGui")
local mainFrame = Instance.new("Frame")
local speedButton = Instance.new("TextButton")
local colorButton = Instance.new("TextButton")
local messageButton = Instance.new("TextButton")

-- Configuração da Interface
screenGui.Parent = player:WaitForChild("PlayerGui")
mainFrame.Parent = screenGui
mainFrame.Size = UDim2.new(0, 300, 0, 400)
mainFrame.Position = UDim2.new(0.5, -150, 0.5, -200)
mainFrame.BackgroundColor3 = Color3.fromRGB(50, 50, 50)

-- Botão para ajustar velocidade
speedButton.Parent = mainFrame
speedButton.Size = UDim2.new(0, 250, 0, 50)
speedButton.Position = UDim2.new(0.5, -125, 0.1, 0)
speedButton.Text = "Ajustar Velocidade"
speedButton.BackgroundColor3 = Color3.fromRGB(100, 100, 255)
speedButton.MouseButton1Click:Connect(function()
    character.Humanoid.WalkSpeed = 20 -- Ajusta a velocidade
end)

-- Botão para mudar cor do ambiente
colorButton.Parent = mainFrame
colorButton.Size = UDim2.new(0, 250, 0, 50)
colorButton.Position = UDim2.new(0.5, -125, 0.3, 0)
colorButton.Text = "Mudar Cor do Ambiente"
colorButton.BackgroundColor3 = Color3.fromRGB(255, 100, 100)
colorButton.MouseButton1Click:Connect(function()
    game.Workspace.CurrentCamera.BackgroundColor3 = Color3.new(math.random(), math.random(), math.random())
end)

-- Botão para mostrar uma mensagem
messageButton.Parent = mainFrame
messageButton.Size = UDim2.new(0, 250, 0, 50)
messageButton.Position = UDim2.new(0.5, -125, 0.5, 0)
messageButton.Text = "Exibir Mensagem"
messageButton.BackgroundColor3 = Color3.fromRGB(100, 255, 100)
messageButton.MouseButton1Click:Connect(function()
    print("Obrigado por usar o painel!")
end)

-- FIM: Mensagem no Console
print("Painel carregado com sucesso!")

-- Configurações
local velocidadeDoClick = 6.0 -- Velocidade do clique em milissegundos
local ativado = false -- Inicialmente desativado

-- Função para alternar entre ativado e desativado
local function alternarAtivacao()
    ativado = not ativado
    if ativado then
        print("Auto Farm ativado!")
    else
        print("Auto Farm desativado.")
    end
end

-- Função para realizar o farming
local function autoFarm()
    while true do
        if ativado then
            -- Lógica para farmar aqui (por exemplo, encontrar e atacar frutos)
            print("Farming...")
            wait(velocidadeDoClick / 1000) -- Espera a velocidade do clique
        else
            wait(1) -- Espera 1 segundo se estiver desativado
        end
    end
end

-- Ativação/desativação com a tecla "E"
game:GetService("UserInputService").InputBegan:Connect(function(input)
    if input.KeyCode == Enum.KeyCode.E then
        alternarAtivacao()
    end
end)

-- Inicia o auto farm
autoFarm()

## GTM Configurations


### Criando um GA

1. Clique em Administrador no menu lateral
2. Clique em Criar Propriedade
3. Preebcha o nome, fuso, moeda
4. Clique em "Mostrar opções avançadas"
5. Ative a opção "Criar uma propriedade do Universal Analytics"
6. Coloque a URL do site
7. Selecione a opção "Criar apenas uma propriedade do Universal Analytics"

### Configurando o GTM

1. Criar uma area de trabalho
2. Criar uma nova tag do GA (UA)
    2.1 Tipo de Tag - Google Analytics: Universal Analytics
    2.2 Tipo de acompanhamento - Visualização de página
    2.3 Configurações do Google Analytics - Criar uma variável
        2.3.1 Tipo de variável - Configurações do Google Analytics
        2.3.2 ID de acompanhamento - Como pegar?
            2.3.2.1 No Analitycs, abrir o Administrador
            2.3.2.2 Na Propriedade, abrir o "Informações de acompanhamento" > "Código de acompanhamento" 
            2.3.2.3 Copie o ID de acompanhamento e use.
        2.3.3 Em "Mais configurações" > "Campos a serem definidos" criar dois campos
            2.3.3.1 allowLinker = true
            2.3.3.2 cookieFlags = samesite=none;secure
    2.4 Acionamento > "All Pages"
3. Criar uma nova tag para Scrolls
    3.1 Tipo de Tag - Google Analytics: Universal Analytics
    3.2 Tipo de acompanhamento - Evento
    3.3 Digite os "Parâmetros de acompanhamento de eventos"
        3.3.1 Categoria = scroll
        3.3.2 Ação = {{Scroll Depth Threshold}}
        3.3.3 Rótulo = {{Page Path}}
        3.3.4 Hit que não é de interação = Verdadeiro
        3.3.5 Configurações do Google Analytics = {{ID_GA-UA}}
    3.4 Acionador, configurar um acionador
        3.4.1 Tipo de acionador = Profundidade de rolagem
        3.4.2 Ative o vertical e digite as porcentagens "25, 50, 75, 100"
        

        


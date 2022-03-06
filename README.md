# Configurando Windows (Desenvolvedor Typescript)

Meu passo a passo de configuração de um Windows 10 (Windows 10 Home Single Language - Versão 21H1)

## Configurando o Terminal Windows

### Instalação

1. Windows Store
2. Baixar e instalar o app "Windows Terminal"
3. Fixar na barra de ferramentas

#### Vinculando o PowerShell 7 no novo terminal

1. [Acessar o repositório do PS7 no Github](https://aka.ms/powershell-release?tag=stable)
2. Baixar a ultima versão `PowerShell-{version}-win-x64.msi` (Para pc's com processador baseado em x64)
3. Instalar usando o instalador baixado
4. Abrir o Terminar Windows
5. Abrir as configurações com `Ctrl + ,`
6. Em `Perfis > + Adicionar novo`
7. Em Linha de comando procure o arquivo baixado (O padrão seria `C:\Program Files\PowerShell\7\pwsh.exe`)
8. Em dirétorio inicial se quiser modificar o caminho inicial desmarque a caixa que diz `Usar o diretório de processo pai`
9. Configurar aparencia à gosto, no meu caso (Para acessar no modo JSON, acesso no menu das configurações a opção `Abrir o arquivo JSON`):

```javascript
{
    "acrylicOpacity": 0.26000000000000001,
    "colorScheme": "One Half Dark",
    "commandline": "C:\\Program Files\\PowerShell\\7\\pwsh.exe",
    "cursorHeight": 50,
    "cursorShape": "vintage",
    "fontFace": "Cascadia Code",
    "fontSize": 10,
    "fontWeight": "medium",
    "icon": "C:\\Program Files\\PowerShell\\7\\assets\\Powershell_av_colors.ico",
    "name": "PowerShell 7",
    "startingDirectory": "D:\\",
    "useAcrylic": true
},
```

10. E por fim no menu, na aba `Inicialização` Selecione seu novo perfil criado

## Configurando o Node

1. Baixar a última versão do NVM (Node Version Manager) para Windows no repositório dele. [Link das versões](https://github.com/coreybutler/nvm-windows/releases)
2. Extraia o instalador e execute-o
3. Vá no site do [Node.js](https://nodejs.org/en/) e veja a versão mais recente (Recomendo a LTS, mas se quiser experimentar pode instalar a versão Current)
4. Use o comando `nvm install 14.17.0` para instalar a versão (No local do 14.17.0 coloque a versão desejada)

## Configurando Ionic

### A IDE, Visual Studio Code

1. Primeiro vamos baixar uma IDE, a minha escolha é Visual Studio Code, [Link de download](https://code.visualstudio.com/)
2. Na etapa de "Selecionar Tarefas Adicionais" marque todas as 4 opções depois de "Outros:"
3. Tenho minhas extensões favoritas, voltadas para me ajudar a desenvolver em Angular, Ionic e Node.js
   1. [Angular Essentials (Version 12)](https://marketplace.visualstudio.com/items?itemName=johnpapa.angular-essentials)
   2. [Ionic Snippets](https://marketplace.visualstudio.com/items?itemName=fivethree.vscode-ionic-snippets)
   3. [Auto Rename Tag](https://marketplace.visualstudio.com/items?itemName=formulahendry.auto-rename-tag)
   4. [Bracket Pair Colorizer](https://marketplace.visualstudio.com/items?itemName=CoenraadS.bracket-pair-colorizer)
   5. [Auto Import](https://marketplace.visualstudio.com/items?itemName=steoates.autoimport)

### Instalando o Git

1. Baixar o instalador, [Link de download](https://git-scm.com/download/win)
2. No instalador, na etapa "Choosing the default editor used by Git", selecione a sua IDE (Meu caso, VS Code)
3. No instalador, na etapa "Adjusting the name of the manual of the initial branch in new repositories", escolha a segunda opção, e mantenha o nome padrão das branchs iniciais em "main"
   4.Finalize o instalador
4. Reinicie o terminal aberto para pegar o Git
5. Vamos configurar o git, mas primeiro verifique se está tudo ok com `git --version`
   1. `git config --global user.name "Seu nome"`
   2. `git config --global user.email "Seu email"`

### Instalando e configurando o Ionic

1. No terminal, execute `npm install -g @ionic/cli` para instala-lo.
2. Agora vamos configurar o que precisamos pra buildar um app Android.
   1. Baixar o [Android Studio](https://developer.android.com/studio).
   2. Finalize o instalador.
   3. Inicie o Android Studio para configura-lo.
   4. No Menu "Install Type" selecione a opção "Custom".
   5. No Menu "SDK Components Setup" selecione a opção "Custom" e salve o local onde a sua SDK está instalado (No meu caso `C:\Users\caio1\AppData\Local\Android\Sdk`).
   6. Aperte em "Finish" para iniciar o processo.
   7. Agora vamos criar algumas variáveis de ambiente
      1. Criar nova variável `ANDROID_SDK_ROOT=C:\Users\caio1\AppData\Local\Android\Sdk`
      2. Editar a variavel PATH com 3 novos caminhos, no meu caso:
         - `C:\Users\caio1\AppData\Local\Android\Sdk\tools\bin`
         - `C:\Users\caio1\AppData\Local\Android\Sdk\platform-tools`
         - `C:\Users\caio1\AppData\Local\Android\Sdk\emulator`
   8. Nesse momento criar um hardware virtual para testarmos o app Ionic
      - Abra a tela inicial do Android Studio
      - Clique em "Configure"
      - Clique em "ADV Manager"
      - Clique em "Create Virtual Device"
      - Escolha o Pixel 2
      - Baixe o Android "Pie"
      - Pronto!
   9. Dessa vez vamos configurar o seu celular pra teste
      - No caso do Windows precisamos de um driver USB OEM
      - Para instalar o driver, encontre o compátivel com a marca do seu celular [neste link](https://developer.android.com/studio/run/oem-usb#Drivers)
      - Rode o comando `adb devices`
      - Caso não tenha aparecido, no aparelho de telefone troque para que o USB usa a conexão USB, exemplo "Somente para carregar", "Transferir Imagens" "MIDI", etc.
      - Quando aparecer, deve ser algo como `RQ8R205WJCK device`
   10. Vamos partir para a parte da JDK, que nesse caso a necessaria e a 8
       - Vamos baixar o arquivo [neste link](https://www.oracle.com/java/technologies/javase/javase-jdk8-downloads.html)
       - Baixe o .exe correspondente ao seu Windows, no meu caso `jdk-8u291-windows-x64.exe`
       - Para baixar você irá precisar de uma conta na Oracle, se não tiver, crie-a
       - Crie uma nova variavel de ambiente `JAVA_HOME=C:\Program Files\Java\jdk1.8.0_291`
       - Adicione um novo caminho na variavel PATH `JAVA_HOME=C:\Program Files\Java\jdk1.8.0_291\bin`
       - Se quiser testar, abra um novo terminal e rode um comando `javac -version`
   11. Agora o Gradle
       - Baixe o Gradle [neste link](https://gradle.org/releases/), de preferencia o mais recente
       - Extraia a pasta dentro
       - Para onde você extraiu, adicione o caminho na variavel de ambiente PATH `D:\gradle-7.0.2\bin`
   12. Instale o Cordova usando um terminal com o comando `npm i -g cordova`
3. Pronto! Se quiser pode testar o build
   1. Crie o app com o `ionic start myApp tabs`
   2. entre na pasta com o `cd myApp`
   3. O prepare para buildar o app Android `ionic cordova prepare android`
   4. Builde o apk com `ionic cordova build android`
   5. Se tiver dado certo, no final aparecerá algo como:

```
in 2m 22s
40 actionable tasks: 40 executed
Built the following apk(s):
D:\codes\myApp\platforms\android\app\build\outputs\apk\debug\app-debug.apk
```

## Configurando o GCloud

1. Abra um terminal e execute o seguinte comando:

```bash
(New-Object Net.WebClient).DownloadFile("https://dl.google.com/dl/cloudsdk/channels/rapid/GoogleCloudSDKInstaller.exe", "$env:Temp\GoogleCloudSDKInstaller.exe")

& $env:Temp\GoogleCloudSDKInstaller.exe
```

2. Finalize o instalador
3. No terminal que aparecer logue usando a conta desejada
4. Escolha o projeto padrão

### Usando o `gcloud`

Repositórios úteis:

[Api's disponíveis](https://github.com/googleapis/google-cloud-node)
[Exemplos](https://github.com/GoogleCloudPlatform/nodejs-docs-samples)

#### Configurando o Cloud Functions con o Cloud Firestore

Links Uteis

[Docs do GCLoud Firetore](https://cloud.google.com/firestore/docs/quickstart-servers#firestore_setup_dataset_pt1-nodejs)

1. Primeiro criamos um novo "Service Account" para ser usado como autenticador com o comando `gcloud iam service-accounts create {name-sa}`
2. Dê permissão de acessos pra ele poder autenticar suas operações. Comando: `gcloud projects add-iam-policy-binding {ID-projeto} --member="serviceAccount:{name-sa}@{ID-projeto}.iam.gserviceaccount.com" --role="roles/owner"`
3. O arquivo será baixado no local onde esta o seu terminal no momento do `Passo 2`
4. Instale o pacote Gcloud Firestore, comando `npm install --save @google-cloud/firestore`
5. Configure o banco no codigo usando o Project ID e o caminho para a sua conta de serviço. Ex.:
```javascript
const Firestore = require("@google-cloud/firestore");

const db = new Firestore({
  projectId: "YOUR_PROJECT_ID",
  keyFilename: "/path/to/keyfile.json",
});
```
6. Caso ainda não tenha ativado a Cloud Build API, vamos ativa-la
   - No console do GCloud 'API's e serviços' > 'Ativar API e serviços'
   - Encontre na item de busca o 'Cloud Build API'
   - Ative-o
7. Agora a configuração do ambiente local
   - Instale a biblioteca 'Functions Framework', ```bash npm install --save-dev @google-cloud/functions-framework ```
   - Agora no package.json vamos criar o script que inicia o servidor local: 
   ```javascript 
   "scripts": {
      "start-local-dev": "npx functions-framework --target=YOUR_FUNCTION_NAME [--signature-type=YOUR_SIGNATURE_TYPE]"
   }
   ```
     - Os tipos de Signature_type podem ser encontrados [aqui](https://cloud.google.com/functions/docs/running/function-frameworks?hl=pt_br#function_types)
   - Para iniciar ``` npm start-local-dev ``` 

20. Pronto para testar!

# Obrigado por ler e bom trabalho!

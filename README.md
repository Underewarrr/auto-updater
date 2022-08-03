# Configuração
## Lembre-se de utilizar o dotnet 4.8!
## Aplicação
### O que faz:
• Verifica a existência da versão local na pasta do cliente;
 
• Se a versão do arquivo não existir, assume que a versão é "1.0" e cria um arquivo de versionamento.
 
• Verifica um arquivo xml no servidor de autenticação.
 
• Baixe atualizações para todas as versões superiores à versão atual do cliente com base em um log de atualizações na pasta local.
 
• Arquivar a versão atualizada na pasta do cliente;
 
• Ao final da atualização o botão deve ser liberado.

### Como Configurar:
 
• Abra o arquivo .sln na pasta "VS Project" com o Visual Studio:
 
Configure o sevidor de atualiazção onde os arquivos de log devem ser subistituidos.

`string Server = "http://localhost/Updates/";`

• Altere para qualquer URL em que você esteja hospedando as atualizações.

![image](https://user-images.githubusercontent.com/74227915/182523674-736acd90-91d4-4acd-a06c-abfc204aa800.png)

Agora vamos pesquisar:
`Process.Start("game.exe", "\\game");`

• Essa função recebe 2 argumentos, nome do executavel e caminho.
 - (altere sem remover o \ \)

![image](https://user-images.githubusercontent.com/74227915/182524283-c8c38477-79de-43ef-a914-6eab2f0add7f.png)

No Visual Studio, selecione o controle WebBrowser (neste caso, nomeie-o como "patchNotes") e altere a url de `http://localhost/` para o caminho do arquivo `index.html`, na pasta do seu servidor que deseja atualizar.

![image](https://user-images.githubusercontent.com/74227915/182524608-2d9279c4-464f-4d69-8767-b8fc6a912c09.png)

 È possivel configurar uma pagina web.
`Exemplo: https://myweb.com/news` e será renderizado no aplicativo

![image](https://user-images.githubusercontent.com/74227915/182659322-e36e152f-2d31-4907-8160-2cc4a94d2dc4.png)

NOTA: Este template padrão é para mostrar a ferramentas e suas features.

Todos os arquivos .html Você pode removê-los e ou editá-los como quiser.

• Agora compile sua solução "Launcher\VS Project\Launcher v2\bin\Debug or Release" 

• Solução compilada coloque o exe e as dlls na pasta do de onde deseja atualizar e inicie a aplicação.

## Como funciona as atualizações na rede

• No servidor do site, após colar a pasta /Updates,Temos um arquivo Updates.xml, para cada atualização adicionamos um `<update> e fechamos com </update>`.
Como no exemplo do arquivo, colocamos o arquivo de atualização em .zip nessa mesma pasta, editando a versão e o nome no arquivo:

• No arquivo version.txt colocamos a versão da nova atualização:
 
• Uma dica para atualizar o .zip é colocar em pastas o caminho do cliente que você deseja atualizar. Exemplo: `assets/textures/world` nesta pasta vamos colocar os arquivos que serão substituídos, no exemplo era Tibia.spr e .dat, estes arquivos são arquivos de sprites!

## oque ainda é necessario fazer manualmente
Compactar o arquivo de atualização em ZIP e colocar na pasta.
Atualizar o arquivo HTML para liberar as atualizações para os clientes.
- Como melhorar 

Interface te atualização no servidor para alterar o arquivo.

### Ao final
Ao abrir o aplicativo ele ira atualizar as referencias, quando o download for finalizado ira liberar o botão.

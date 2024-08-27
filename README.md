# Bot Slack

Este projeto é um bot Slack que conta mensagens enviadas pelos usuários e fornece um endpoint para consultar o número de mensagens de um usuário específico.

## Requisitos

Antes de começar, você precisará ter as seguintes ferramentas instaladas:

- [Python 3.x](https://www.python.org/)
- [ngrok](https://ngrok.com/) (para expor o servidor local para o Slack)

## Configuração

1. **Clone o Repositório**:

    ```bash
    git clone https://github.com/AlanBReis/bot-slack.git
    cd bot-slack
    ```

2. **Instale as Dependências**:

    Crie um arquivo `requirements.txt` com o seguinte conteúdo e instale as dependências:

    ```plaintext
    Flask==2.0.3
    slack-sdk==3.11.0
    slackeventsapi==2.3.0
    python-dotenv==0.21.1
    ```

    Instale as dependências com:

    ```bash
    pip install -r requirements.txt
    ```

3. **Crie um Arquivo `.env`**:

    Na raiz do projeto, crie um arquivo `.env` e adicione suas variáveis de ambiente:

    ```plaintext
    SLACK_TOKEN=your-slack-token
    SIGNIN_SECRET=your-signin-secret
    ```

4. **Configure o ngrok**:

    - **Instale o ngrok**: Se ainda não tiver, faça o download e instale a partir do [site oficial](https://ngrok.com/download).
    - **Inicie o ngrok**: Abra um terminal e execute o comando para criar um túnel para a porta onde seu servidor Flask está rodando (por exemplo, 5000):

      ```bash
      ngrok http 5000
      ```

    - **Copie o URL do ngrok**: Você verá um URL público (como `https://xxxxxx.ngrok.io`). Esse URL será usado para configurar o Slack.

5. **Configure o Slack**:

    - Vá até o painel de administração do Slack e configure o URL de eventos para o URL do ngrok que você copiou, com a rota `/slack/events`.

6. **Execute o Servidor Flask**:

    ```bash
    python bot.py
    ```

7. **Verifique se o ngrok está em execução**:

    O ngrok deve estar rodando e exibindo o URL público. Certifique-se de que o ngrok e o servidor Flask estejam ambos ativos.

## Estrutura do Projeto

- `bot.py`: Código principal do bot.
- `.env`: Arquivo de variáveis de ambiente (não versionado no Git).
- `requirements.txt`: Lista de dependências do projeto.

## Contribuições

Sinta-se à vontade para contribuir com melhorias, correções ou novas funcionalidades. Faça um fork do repositório e envie um pull request!

## Licença

Este projeto é licenciado sob a [MIT License](LICENSE).

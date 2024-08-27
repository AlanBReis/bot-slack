## Requisitos

Antes de rodar o projeto, certifique-se de ter as seguintes ferramentas instaladas:

- [Python 3.x](https://www.python.org/)
- [ngrok](https://ngrok.com/) (para expor o servidor local para o Slack)

## Configuração do ngrok

1. **Instale o ngrok**: Se ainda não tiver, faça o download e instale o ngrok a partir do [site oficial](https://ngrok.com/download).

2. **Inicie o ngrok**: Abra um terminal e execute o seguinte comando para criar um túnel para a porta onde seu servidor Flask está rodando (por exemplo, 5000):

    ```bash
    ngrok http 5000
    ```

3. **Copie o URL do ngrok**: Após iniciar o ngrok, você verá um URL público (como `https://xxxxxx.ngrok.io`). Esse URL será usado para configurar o Slack para redirecionar eventos para seu bot.

4. **Configure o Slack**: Vá até o painel de administração do Slack e configure o URL de eventos para o URL do ngrok que você copiou. A rota será algo como `https://xxxxxx.ngrok.io/slack/events`.

## Executando o Bot

1. **Clone o Repositório**:

    ```bash
    git clone https://github.com/AlanBReis/bot-slack.git
    cd bot-slack
    ```

2. **Instale as Dependências**:

    ```bash
    pip install -r requirements.txt
    ```

3. **Crie um Arquivo .env**: Crie um arquivo `.env` na raiz do projeto e adicione suas variáveis de ambiente:

    ```plaintext
    SLACK_TOKEN=your-slack-token
    SIGNIN_SECRET=your-signin-secret
    ```

4. **Execute o Servidor Flask**:

    ```bash
    python bot.py
    ```

5. **Inicie o ngrok**:

    ```bash
    ngrok http 5000
    ```

Agora seu bot deve estar rodando e acessível através do URL público fornecido pelo ngrok.

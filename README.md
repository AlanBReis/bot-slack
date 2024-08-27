# Bot de Automação com Python e Slack API

Este projeto é um bot desenvolvido em Python que usa a Slack API para automatizar tarefas como abertura de tickets e respostas a perguntas frequentes. O bot também envia notificações e pode ser integrado com sistemas CI/CD.

## Funcionalidades

- Abertura de tickets
- Respostas a perguntas frequentes
- Gerenciamento de recursos em nuvem
- Notificações via Slack, Discord, ou email
- Integração com Jenkins e GitHub Actions

## Instalação

1. Clone o repositório:
    ```bash
    git clone https://github.com/AlanBReis/bot-slack.git
    cd bot-slack
    ```

2. Crie e ative um ambiente virtual:
    ```bash
    python -m venv venv
    source venv/bin/activate  # No Windows: venv\Scripts\activate
    ```

3. Instale as dependências:
    ```bash
    pip install -r requirements.txt
    ```

4. Configure o arquivo `.env` com as variáveis necessárias.

## Configuração do ngrok

Para expor seu servidor local para a internet e permitir que a Slack API se comunique com ele, você pode usar o ngrok:

1. Inicie o ngrok para criar um túnel HTTP:
    ```bash
    ngrok http 5000
    ```

2. O ngrok fornecerá uma URL pública. Atualize suas configurações de webhook no Slack para usar essa URL.

## Uso

- **Executar o Bot**:
    ```bash
    python bot.py
    ```

- **Exemplo de Comando**:
    - Para abrir um ticket:
        ```bash
        /bot_ticket_open "Título do Ticket" "Descrição do Ticket"
        ```

## Integração CI/CD

Veja os arquivos `Jenkinsfile` e `.github/workflows/main.yml` para exemplos de configuração CI/CD.

## Contribuição

1. Faça um fork do repositório.
2. Crie uma nova branch:
    ```bash
    git checkout -b minha-nova-funcionalidade
    ```
3. Faça as alterações e commit:
    ```bash
    git commit -m "Adiciona nova funcionalidade"
    ```
4. Envie para a branch original:
    ```bash
    git push origin minha-nova-funcionalidade
    ```
5. Crie um Pull Request.

## Licença

Este projeto está licenciado sob a [MIT License](LICENSE).

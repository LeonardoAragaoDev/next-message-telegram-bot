# 🤖 next-message-telegram-bot

**Next Message Bot for Telegram Channels**

O **@NextMessageBot** é uma solução de automação poderosa projetada para canais do Telegram. Ele permite configurar uma mensagem de resposta automática (conhecida como "Next Message" ou mensagem de seguimento) que é disparada toda vez que uma nova postagem é publicada no seu canal.

Isso é ideal para incluir botões de reação, links de comentários, ou qualquer chamada para ação crucial logo abaixo do seu conteúdo principal, garantindo alta fidelidade de formatação (incluindo mídias e botões).

---

## ✨ Recursos Principais

-   **Automação de Resposta:** Dispara uma mensagem configurada após cada novo post no canal.
-   **Alta Fidelidade:** Usa `copyMessage` para replicar perfeitamente o conteúdo original (texto, mídia, botões inline).
-   **Modos de Envio Flexíveis:** Escolha se a mensagem de resposta deve ser enviada como um **Reply** (resposta) ao post principal ou como uma **Nova Mensagem** separada.
-   **Fluxo de Configuração Amigável:** Interface de configuração passo a passo via chat privado.

---

## 🔗 Demonstração e Comunidade

Confira o bot em ação e junte-se à nossa comunidade:

| Recurso                | Link                                                        |
| :--------------------- | :---------------------------------------------------------- |
| **Bot Oficial**        | 👉 [@NextMessageBot](https://t.me/NextMessageBot)           |
| **Canal de Novidades** | 👉 [@BotNovidades](https://t.me/BotNovidades)               |
| **Grupo de Discussão** | 👉 [Grupo do @BotNovidades](https://t.me/+7Igu38iX7Ns5YjUx) |
| **Dev** | 👉 [Desenvolvedor do Bot](https://t.me/LeonardoAragao) |

---

## 🛠️ Instalação e Configuração Local

Este projeto é construído em **PHP** usando o framework **Laravel** e a biblioteca `irazasyed/telegram-bot-sdk`.

### Pré-requisitos

1.  PHP (Versão compatível com Laravel).
2.  Composer.
3.  Um banco de dados (Ex: MySQL, PostgreSQL).
4.  Um túnel de acesso público (Ex: **ngrok** ou **Expose**) para expor sua URL local.

### 1. Clonar o Repositório

```bash
git clone git@github.com:seu-usuario/next-message-telegram-bot.git
cd next-message-telegram-bot
```

### 2. Instalar dependências

```bash
composer install
```

### 3. Configuração do Ambiente (.env)

```env
# --- Configuração Geral do Laravel ---
APP_NAME="Next Message Bot"
APP_ENV=local
APP_DEBUG=true
APP_URL=http://localhost:8000 # Substitua pela sua URL pública (ngrok/Expose)

# --- Configuração do Banco de Dados ---
DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=db
DB_USERNAME=user
DB_PASSWORD=pass

# --- Configuração do Telegram ---
TELEGRAM_BOT_TOKEN="SEU_TOKEN_DO_BOT_AQUI"

# IDs de canais essenciais para o funcionamento do bot
# Estes IDs devem ser obtidos do seu BotFather e canais criados.
# O STORAGE_CHANNEL_ID é um canal privado onde o bot armazena as mensagens de resposta.
TELEGRAM_STORAGE_CHANNEL_ID="-100XXXXXXXXXXXXXXXX"
TELEGRAM_ADMIN_CHANNEL_ID="-100YYYYYYYYYYYYYYYYY"
TELEGRAM_ADMIN_CHANNEL_INVITE_PRIVATE_LINK="[https://t.me/c/](https://t.me/c/)..." # Link de convite do seu canal admin/novidades
```

### 4. Rodar Migrações

```bash
php artisan migrate
```

### 5. Iniciar o Servidor (e o Túnel Público)

Inicie o servidor local do Laravel:

```bash
php artisan serve
```

Em uma janela separada, inicie o túnel público (Ex: ngrok) e anote a URL gerada (por exemplo, `https://abcdefg.ngrok-free.app`).

### 6. Configurar o Webhook do Telegram

Finalmente, você deve informar ao Telegram qual URL ele deve usar para enviar as atualizações (webhooks). Substitua `TOKEN_DO_SEU_BOT` e `URL_PUBLICA_NA_WEB` na URL abaixo e acesse-a no seu navegador:

```bash
https://api.telegram.org/botTOKEN_DO_SEU_BOT/setWebhook?url=URL_PUBLICA_NA_WEB/api/telegram/webhook
```

Exemplo com ngrok:

```bash
https://api.telegram.org/bot123456:ABC-DEF123456/setWebhook?url=https://abcdefg.ngrok-free.app/api/telegram/webhook
```

Se a configuração for bem-sucedida, você verá uma resposta JSON do Telegram.

### 🤝 Contribuição

Contribuições são sempre bem-vindas! Sinta-se à vontade para abrir uma issue ou enviar um _pull request_.

### 📄 Licença

Este projeto está sob a licença [GPL-3.0](https://github.com/LeonardoAragaoDev/next-message-telegram-bot/blob/master/LICENSE).

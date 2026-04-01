# chatty-bot

whatsapp ai agent that chats with your contacts using gemini.

## setup

```bash
npm install
```

create `.env`:
```
GEMINI_API_KEY=your_key_here
```

run it:
```bash
npm start
```

scan qr code with whatsapp (settings > linked devices).

## usage

save a contact:
```
save:john:1234567890
```

start ai agent:
```
agent:john:you are a friendly helpful assistant
```

the bot will handle messages from john automatically.

stop agent:
```
stop:john
```

other commands:
- `agents` - list active agents
- `contacts` - list saved contacts  
- `send:john:hello` - manual message
- `history:john` - view chat history
- `clear:john` - clear history
- `exit` - quit

## how it works

uses baileys for whatsapp web api, gemini for ai responses. batches rapid messages (4s delay) before replying. stores chat history for context. works in dms and groups.

## security

don't commit:
- `.env` (api keys)
- `auth_info/` (whatsapp session)
- `contacts.json` (personal data)
- `chat_history/` (conversations)

already gitignored.

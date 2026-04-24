# ⏱ CallTimeTracker — Vencord Plugin

> Descubra quanto tempo total você já ficou em chamada com seus amigos no Discord.

---

## O que esse plugin faz?

O **CallTimeTracker** é um plugin para o [Vencord](https://vencord.dev) que **soma automaticamente todo o tempo de chamadas que você teve com uma pessoa em DM**, desde o início do histórico da conversa.

Sabe quando o Discord lançou o Recap de fim de ano e mostrou quantas horas você ficou em call com seus melhores amigos? Esse plugin faz exatamente isso — mas disponível a qualquer momento, para qualquer amigo, direto no cliente.

### Como funciona?

O Discord registra automaticamente mensagens de sistema no chat sempre que uma chamada termina, com frases como:

> *"Lunar iniciou uma chamada que durou 1 hora e 23 minutos."*

O plugin varre todo o histórico da DM, coleta essas mensagens, extrai o tempo de cada chamada e soma tudo — te dando o total real acumulado desde que vocês começaram a se falar.

---

## O que ele mostra?

Ao clicar com o botão direito em um amigo e selecionar **"⏱ Ver Tempo de Chamadas"**, um modal abre com:

- ⏱ **Tempo total** em chamadas (ex: `4d 7h 32m`)
- 📞 **Número de chamadas** realizadas
- 📵 **Chamadas perdidas** (sem resposta)
- 📅 **Data da primeira e última chamada**
- 🕐 **Média de duração** por chamada

---

## Instalação

### Pré-requisitos
- Discord instalado
- [Vencord](https://vencord.dev) instalado
- Node.js + pnpm

### Passo a passo

```bash
# 1. Clone o Vencord
git clone https://github.com/Vendicated/Vencord
cd Vencord

# 2. Instale as dependências
npm install -g pnpm
pnpm install

# 3. Crie a pasta do plugin
mkdir src/userplugins/CallTimeTracker

# 4. Coloque o index.tsx dentro dessa pasta
# (baixe o arquivo desse repositório)

# 5. Compile e injete
pnpm build
pnpm inject
```

Depois, reinicie o Discord, vá em **Configurações → Plugins**, procure por **CallTimeTracker** e ative.

---

## Como usar

1. Clique com o **botão direito** no nome ou avatar de qualquer amigo
2. Clique em **"⏱ Ver Tempo de Chamadas"**
3. Aguarde a leitura do histórico (alguns segundos)
4. Veja as estatísticas!

---

## Configurações

| Opção | Descrição | Padrão |
|---|---|---|
| `startYear` | Ano de início da contagem | `2024` |
| `showMissedCalls` | Exibir chamadas perdidas | `true` |

---

## Limitações

- Funciona **apenas em DMs** (mensagens diretas) — servidores não registram duração de chamadas nas mensagens de sistema
- Conta apenas chamadas **a partir do ano configurado**
- Requer que o histórico da conversa esteja acessível (conversas antigas muito deletadas podem ter lacunas)

---

## Tecnologia

O plugin não usa nenhuma API externa nem armazena dados em servidor. Tudo é processado localmente, lendo apenas as mensagens de sistema que o próprio Discord já registrou na sua conversa.

---

*Plugin não oficial. Uso sujeito aos Termos de Serviço do Discord.*
-Feito por @lunaridade (Discord) com uso de Ia, pode ocorrer erros e não ser perfeito.

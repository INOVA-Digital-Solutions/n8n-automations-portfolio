# Classificador de Tarefas com n8n



Automação que classifica tarefas por prioridade usando Switch e as direciona para Trello, Slack ou Google Sheets.

Equipes recebiam tarefas sem triagem, causando sobrecarga e falta de organização. Era necessário classificar automaticamente cada item por prioridade.

Este workflow identifica a prioridade de cada tarefa (Setados via Set) 
(`alta`, `media`, `baixa`) e encaminha para o destino correto, finalizando com um aviso em determinadocanal no discord.

---
<img width="1054" height="354" alt="image" src="https://github.com/user-attachments/assets/38df1d9f-b629-48d2-a986-fdbeb12efe8b" />

---

## Tecnologias
- n8n
- Trello API
- Slack API
- Google Sheets API
- Discord Webhook

## Fluxo
1. O workflow recebe uma lista de tarefas.
2. Cada tarefa é convertida em item individual.
3. O Switch avalia `priority`.
4. Cada prioridade é direcionada para um serviço diferente.
5. Um aviso éenviado a um canal do discord avisando final do fluxo.

## Como rodar
1. Baixe o arquivo `workflow.json`.
2. No n8n: Menu > Import From File
3. Configure credenciais de Trello/Slack/Sheets.



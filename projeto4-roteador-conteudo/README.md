
# Roteador de Conteúdo Inteligente com Switch e If

Automação que classifica e direciona posts automaticamente usando **Switch** e **If**, simulando um roteador de decisão para múltiplos tipos de conteúdo.

Com a necessidade de organizar posts enviados por usuários e tratá-los de forma diferente conforme suas características: tipo do conteúdo, tamanho do texto e presença de palavras proibidas.
O objetivo era criar um fluxo simples, mas inteligente, capaz de direcionar cada post para o destino correto, sem necessidade de processamento manual.

Este workflow recebe posts simulados via **Set**, analisa tipo (`type`) e score de qualidade, aplicando um **Switch** para roteamento principal e um **If** secundário para validação adicional.
Cada categoria pode ser enviada a um destino diferente (ex.: Webhook Response, Discord, Slack, Sheets etc.).

---

<img width="774" height="344" alt="image" src="https://github.com/user-attachments/assets/fca3aa9f-5c6b-4ea5-ac53-003e60cc8370" />


---

## Tecnologias

* n8n
* Switch
* If
* Set
* Google Sheets (para simular saída final)

---

## Fluxo

1. O workflow cria uma lista de posts usando **Set**, simulando entradas reais de usuários.
2. O **Switch** avalia o campo `type` do post (ex.: `texto`, `imagem`, `video`).
3. Cada tipo segue para um caminho específico de processamento.
4. Um **If** opcional valida regras adicionais — como score mínimo.
5. Os posts aprovados são enviados para um destino simulado (Google Sheets).

---

## Como rodar

1. Baixe o arquivo `workflow.json`.
2. No n8n: **Menu > Import From File**
3. Execute manualmente e observe como cada post é roteado automaticamente.
4. Ajuste regras do Switch/If conforme o tipo de conteúdo que deseja simular.



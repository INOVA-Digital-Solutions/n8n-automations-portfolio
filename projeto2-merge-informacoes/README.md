
# Merge de Informações de Usuários

Automação que unifica dados de usuários usando **Merge by Key** e envia o resultado consolidado para Google Sheets ou Webhook(fallback).

Os dados estavam separados em duas fontes:
uma com informações básicas (nome, email) e outra com métricas (login_count, last_access).
Isso gerava inconsistências e dificultava análises.
Era necessário combinar ambas automaticamente em um fluxo simples.

Este workflow recebe duas listas (Set → lista A e Set → lista B),
as transforma em itens individuais e unifica tudo usando **Merge** configurado com chave `Id`.

---

<img width="972" height="331" alt="image" src="https://github.com/user-attachments/assets/fce66555-6c44-42ef-aa31-90bd9cd88fdd" />


---

## Tecnologias

* n8n
* Merge (Merge by Key)
* Google Sheets API
* Webhook Response

## Fluxo

1. O workflow recebe **Lista A** e **Lista B** com dados básicos de forma paralela.
2. As listas são convertidas em itens individuais de forma paralela.
3. O Merge combina A + B usando a chave `id`.
4. É realizada uma formatação dos campos para utilizar no Google Sheets
5. É realizada uma validação para checar se algum dos campos está vazio, enviando para fallback caso sim.
6. O resultado unificado é enviado para Google Sheets, com a devida formatação.

## Como rodar

1. Baixe o arquivo `workflow.json`.
2. No n8n: **Menu > Import From File**
3. Configure credenciais (caso use Google Sheets).

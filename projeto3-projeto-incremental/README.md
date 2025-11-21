# Processamento de Grandes Listas com Split in Batches

Automação que processa listas extensas em partes usando **Split in Batches**, envia cada lote para processamento via API fictícia e reconstrói o resultado final usando **Merge (Append)**.

Havia a necessidade de processar uma lista grande de itens (ex.: IDs) sem estourar limites de API nem sobrecarregar o fluxo.
Para isso, o processamento foi dividido em blocos de 10 itens, garantindo melhor controle, performance e escalabilidade.

Este workflow recebe uma lista inicial (Set → 40 itens), divide em batches de 10 usando **Split in Batches**, processa cada lote via HTTP Request, e ao final reconstrói tudo com **Merge (Append)** para produzir uma única saída consolidada.

---

<img width="702" height="210" alt="image" src="https://github.com/user-attachments/assets/d2b50b25-f3aa-473c-b77d-236f7f97a311" />


---

## Tecnologias

* n8n
* Split in Batches
* HTTP Request
* Merge (Append)
* Webhook Response (para exibir o resultado final)

---

## Fluxo

1. O workflow cria uma lista inicial de **40 itens** usando um Set.
2. O **Split in Batches** divide a lista em lotes de 10 itens.
3. Cada lote é enviado para um **HTTP Request** (API fictícia usando POST).
4. O retorno de cada batch é agregado imediatamente com um **Merge (Append)**.
5. O loop continua até todos os batches serem processados.
6. O resultado consolidado (40 itens) é retornado via Webhook Response.

---

## Como rodar

1. Baixe o arquivo `workflow.json`.
2. No n8n: **Menu > Import From File**
3. Execute manualmente → verifique cada batch sendo processado em loop.
4. Ajuste o tamanho do batch conforme a necessidade do seu caso de uso.

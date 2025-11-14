# 🚀 Projeto de Análise de Dados: Dashboard de Tickets de Suporte

Este projeto é um dashboard interativo criado no Power BI para analisar um conjunto de dados real de tickets de suporte técnico. O objetivo é transformar dados brutos em insights acionáveis, identificando gargalos, prioridades e as causas-raiz dos chamados.

<img width="1232" height="694" alt="image" src="https://github.com/user-attachments/assets/a73b6051-fd7a-4d1f-8cc9-7066f2f02a5b" />


---

### 🛠️ Ferramentas Utilizadas
* **Power BI** (Visualização e Modelagem)
* **Power Query** (Extração, Transformação e Carga - ETL)
* **Linguagem M** (Implicitamente, para o tratamento dos dados)

---

### 📈 O Processo de Análise (ETL)

[aa_dataset-tickets-multi-lang-5-2-50-version.csv](https://github.com/user-attachments/files/23551065/aa_dataset-tickets-multi-lang-5-2-50-version.csv)

Os dados brutos (do arquivo `aa_dataset-tickets-multi-lang-5-2-50-version.csv`) estavam "sujos" e não prontos para análise. O seguinte processo de ETL foi aplicado no Power Query:

1.  **Limpeza de Colunas:** Colunas com excesso de valores nulos (como `tag_3` até `tag_8`) foram removidas para focar a análise e melhorar a performance.
2.  **Tratamento de Nulos:** Valores `null` na coluna `subject` (Assunto) foram substituídos por `"Sem Assunto"`, garantindo que nenhum registro fosse perdido durante a contagem.
3.  **Verificação de Tipos:** Todos os dados foram checados e ajustados para seus tipos corretos (ex: `queue` e `priority` como Texto).

---

### 📊 Insights Respondidos pelo Dashboard

O dashboard foi construído para responder 4 perguntas-chave de negócio:

1.  **Qual o Volume Total?**
    * **28.587** chamados totais.
    * **5** filas de atendimento distintas.

2.  **Onde está o Gargalo?**
    * O gráfico de barras "Contagem por Queue" identifica quais filas (`Technical Support`, `Billing`, etc.) recebem o maior volume de chamados.

3.  **Qual a Urgência?**
    * O gráfico de pizza "Contagem por Priority" mostra a proporção de chamados `high`, `medium` e `low`, permitindo focar no que é mais crítico.

4.  **Qual o Motivo?**
    * O mapa de árvore "Contagem por tag_1" revela os principais motivos de abertura de chamados (como `Security`, `Product`, `Account`), identificando a causa-raiz dos problemas.

O dashboard é totalmente interativo, permitindo filtrar os motivos e prioridades por cada fila de atendimento.

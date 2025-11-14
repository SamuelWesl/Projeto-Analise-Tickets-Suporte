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

---

## 🚀 Atualização V2.0: Migração para Arquitetura SQL

Este projeto foi atualizado para demonstrar a evolução de uma análise simples (baseada em CSV) para uma arquitetura de dados profissional, simulando um ambiente corporativo real.

O dashboard, que antes lia dados de um arquivo `.csv`, agora está conectado **diretamente a um banco de dados PostgreSQL**.

### O Novo Processo:
<img width="2056" height="1168" alt="image" src="https://github.com/user-attachments/assets/8087aedb-6db2-40d7-a263-d22ac55348ee" />


1.  **Backend (SQL):** Os dados limpos (28.587 registros) foram migrados do arquivo `tickets_limpo.csv` para uma tabela (`tickets_suporte`) dentro de um servidor PostgreSQL.
2.  **Frontend (Power BI):** O Power BI agora obtém seus dados usando uma conexão direta com o banco PostgreSQL (`localhost`), provando a capacidade de integração com fontes de dados relacionais.

### 🛠️ Ferramentas Utilizadas (V2.0)

* **Power BI** (Visualização e Modelagem)
* **Power Query** (Tratamento de Nulos na conexão)
* **PostgreSQL** (Armazenamento de Dados / Backend)
* **pgAdmin** (Gerenciamento do Banco de Dados e Importação)

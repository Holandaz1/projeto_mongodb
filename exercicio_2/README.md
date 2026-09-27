# Cartola FC ETL (MongoDB)

## Arquivos
- `cartola_etl.py`: Script principal (orquestra ETL).
- `requirements.txt`: Dependências do projeto.
- `.env.example`: Exemplo de configuração de ambiente.

## Como executar
1. Crie um ambiente virtual (opcional):
   ```bash
   python -m venv .venv
   source .venv/bin/activate  # Linux/Mac
   .venv\Scripts\activate   # Windows
   ```

2. Instale as dependências:
   ```bash
   pip install -r requirements.txt
   ```

3. Crie o arquivo `.env` com base no `.env.example` e ajuste `MONGO_URI` conforme seu cluster MongoDB.

4. Execute:
   ```bash
   python cartola_etl.py
   ```

## Observações
- O script grava em três coleções no DB `cartola_fc_db`:
  - `clubes_rodada_atual` (upsert por `_id`)
  - `atletas_rodada_atual` (limpa e insere a coleta atual)
  - `mercado_rodada_atual` (mantém somente o registro mais recente)

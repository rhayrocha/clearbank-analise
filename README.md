# ClearBank - Análise Financeira com Python

Desafio prático de análise de transações bancárias da fintech ClearBank, processando dados brutos de movimentações financeiras, aplicando regras de validação e descarte, agregando métricas mensais, identificando anomalias financeiras e exportando os relatórios em formato JSON e visualização gráfica.

## 🛠️ Tecnologias e Módulos Utilizados
- **Python 3.10+**
- Módulos nativos: `csv` (via `DictReader`), `json`, `datetime`
- Biblioteca de visualização: `matplotlib`

## 📋 Regras de Validação e Limpeza
O pipeline analisa cada registro do arquivo `transacoes.csv` e descarta silenciosamente linhas que possuam:
- `id` vazio ou não inteiro;
- `cliente_id` nulo ou em branco;
- `data` fora do padrão estrito `AAAA-MM-DD`;
- `tipo` diferente de `credito` ou `debito`;
- `valor` não numérico ou menor/igual a zero.

Registros com valores superiores a R$ 10.000,00 são classificados e auditados como **transações suspeitas**.

## 🚀 Como Executar
1. Certifique-se de que o arquivo `transacoes.csv` está na mesma pasta do notebook.
2. Abra o arquivo `desafio-final.ipynb` no Jupyter Notebook, VS Code ou Google Colab.
3. Execute todas as células em ordem (`Run All`).

## 📊 Arquivos Gerados
- `relatorio.json`: Resumo estruturado com auditoria de linhas, período analisado, métricas por mês e lista de suspeitas.
- `grafico.png`: Gráfico de barras demonstrando o saldo líquido por mês.
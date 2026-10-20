# Análise de Churn: Conecta Telecom

Modelagem estatística para responder a uma pergunta de negócio: **quais fatores levam os clientes a cancelar o serviço?**

> A Conecta Telecom é uma empresa fictícia. Todos os dados foram gerados por simulação, para fins de estudo.

**[Ver a página da análise](https://saviols6.github.io/analise-churn-conecta/)**

## Principais resultados

| Fator | Odds ratio | Leitura |
| :--- | ---: | :--- |
| Contrato mensal (vs anual) | 78,5 | Chance de churn cerca de 78 vezes maior |
| Fibra óptica (vs DSL) | 3,11 | Chance cerca de 3 vezes maior |
| Fatura mensal (+R$ 1) | 1,026 | +2,6% de chance a cada real |
| Fidelidade (+1 mês) | 0,950 | −5,0% de chance a cada mês de casa |
| Contrato de dois anos (vs anual) | 0,42 | Chance cerca de 58% menor |
| Sem internet (vs DSL) | 0,96 | Não significativo (p = 0,85) |

- Taxa de churn geral: **41,8%** em 2.000 clientes
- Pseudo R² (McFadden): **0,434**
- Perfil de maior risco: contrato mensal, até 12 meses de casa, fibra óptica e fatura acima da mediana

## Arquivos

| Arquivo | Conteúdo |
| :--- | :--- |
| `index.html` | Página de apresentação com gráficos interativos (Plotly.js) e seletor de tema claro/escuro |
| `Mini_projeto_5.ipynb` | Notebook com geração dos dados, análise exploratória, regressão logística e interpretação |
| `resultados.json` | Resultados exportados pelo notebook e usados pela página |

## Como reproduzir

1. Instale as dependências: `pandas`, `numpy`, `statsmodels`, `seaborn`, `matplotlib`, `plotly`.
2. Execute o notebook `Mini_projeto_5.ipynb` do início ao fim. A última seção gera o `resultados.json`.

## Metodologia

- Regressão logística (`statsmodels.Logit`) com as variáveis fidelidade, fatura mensal, tipo de contrato e serviço de internet.
- Variáveis categóricas convertidas em dummies. Categorias de referência: contrato **Anual** e internet **DSL**.
- Significância considerada com p ≤ 0,05.
- Associação não implica causalidade, e o modelo não foi validado fora da amostra.

---

Autor: Sávio Giovani

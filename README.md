# Predição de Risco em Seguro de Frotas PJ (Trillia RiskPack)

## Integrantes
- Grupo 5: Breno, Danyllo, Ernesto, Juliana, Karine e Rayanne

## Objetivo
Desenvolver uma solução de Machine Learning (Random Forest OOT) acoplada ao Motor de Decisão 3-Way (Trillia RiskPack) para estimar a probabilidade de sinistro de casco (ALVO_CASCO) em frotas automotivas PJ e otimizar o resultado operacional da seguradora no momento pré-emissão.

## Problema
Sem inteligência analítica pré-emissão, seguradoras aceitam ou subprecificam frotas de alto risco, elevando despesas com indenizações e comprometendo o ganho operacional. Na carteira simulada, sinistros em frotas de altíssimo risco geraram perdas milionárias evitáveis.

## Tecnologias
- Python 3.12
- Scikit-learn (RandomForestClassifier, Metrics)
- Pandas & NumPy
- Matplotlib & Seaborn
- XML
- Google Colab

## Estrutura do Projeto
```
Grupo 5 - Projeto Final/
│
├── README.md
├── requirements.txt
│
├── docs/
│   ├── Relatorio_Tecnico_Final_Frotas_PJ.docx
│   └── politica_credito_frotas.xml
│
├── data/
│   ├── raw/
│   │   └── cesar_residencia_trillia_frota_pj_mercado.csv
│   ├── processed/
│   │   └── resultado_motor_decisao_frotas.csv
│   └── external/
│
├── notebooks/
│   └── colab_projeto_final.ipynb
│
├── presentation/
│   └── [GRUPO 5] Pitch_Final_Frotas_PJ.pptx
```

## Como Executar
1. Acesse o [Google Colab](https://colab.research.google.com/).
2. Faça o upload do arquivo `notebooks/colab_projeto_final.ipynb`.
3. Na **TAREFA 1**, faça o upload da base de dados bruta `data/raw/cesar_residencia_trillia_frota_pj_mercado.csv`.
4. Execute todas as células em sequência (`Ambiente de Execução` -> `Executar Tudo`).
5. Ao final da **TAREFA 6**, a base de resultados simulada `resultado_motor_decisao_frotas.csv` será exportada automaticamente.

## Resultados
- **Desempenho do Modelo**: AUC-ROC = 0,92 no split Out-of-Time (Treino até Jun/2023, Teste Jul/2023 a Fev/2024).
- **Ordenação por Decil**: Concentração de 82,15% de todos os sinistros da carteira nos Decis 1 a 3 (44,9% das ocorrências isoladas no Decil 1).
- **Volumetria Operacional do Motor (3.932 apólices)**:
  - **APROVADO (Fast-track)**: 2.569 apólices (65,34%)
  - **ACEITO COM CONDIÇÃO (Resgate GPS + 15% Agravamento)**: 876 apólices (22,28%), resgatando 137 frotas de alto risco.
  - **RECUSADO (Recusal Sumária)**: 487 apólices (12,39%)
- **Impacto Financeiro Simulado**:
  - **R$ 5,13M** em Sinistros Evitados (114 frotas com sinistro real barradas).
  - **R$ 760K** em Receita Adicional por Agravamento Tarifário.

## Demonstração
- O notebook interativo no Colab executa a validação OOT, treina o modelo Random Forest, gera a especificação XML da política de subscrição (`politica_credito_frotas.xml`), instancia o motor de decisão e processa 100% da carteira, salvando a base final de auditoria com os KPIs operacionais e financeiros.

## Referências
- CRISP-DM Consortium. Cross-Industry Standard Process for Data Mining. 2000.
- Breiman, L. Random Forests. Machine Learning, 45(1), 5-32. 2001.
- Base de dados Trillia. 2026.

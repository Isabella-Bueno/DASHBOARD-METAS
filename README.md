#  ESTUDE DE CADO - DASHBOARD DE META: 2º MAIOR EMPRESA DO BRASIL


## 📝 Cenário: 
A empresa fictícia de Atendimento ao Cliente ATIVA possui uma grande operação de Call Center em 3 regiões do Brasil
(Nordeste, Sudeste e Sul).
A ATIVA tem como meta se tornar a 2ª maior empresa do Brasil em 2 anos, hoje ela é a 3ª colocada e para isso precisa melhorar os
seus níveis de qualidade para assim conseguir mais clientes, pois esses índices de qualidade atrapalharam o fechamento de 2 grandes
contratos no último ano.

## 🎯 Objetivos do Dashboard

► Analisar os Indicadores por Região e por Período (últimos 2 anos)

► Analisar os seguintes KPI´s:
    
  ### Market Share:
      Posição da Empresa no Ranking Nacional
      Comparar Faturamento da Empresa com o 2º colocado e a variação (diferença) do Faturamento
      Meta: 2º Colocado
      
  ### Lucratividade
      Fórmula: (Lucro Líquido / Receita Total) * 100
      Meta: 25%
      
  ### Churn Rate:
      Fórmula: Total de Clientes Cancelados/Total de Clientes Ativos
       Meta: 2%
       
  ### Turnover Geral:
      Fórmula: ((Total Admissões + Total de Demissões)/2)/Total de Colaboradores Ativos
      Meta: Até 5,5% ao mês
  ### NPS (Net Promoter Score):
       Fórmula: Percentual Promotores - Percentual Detratores
       Meta: >=20 ao mês
  ### CSAT (Customer Satisfaction Score)
       Fórmula: Total de Clientes Satisfeitos/Total de Clientes que responderam a pesquisa
       Meta: Até 70% ao mês
 ► Analisar os Indicadores por Região e por Período (últimos 2 anos)
 
 ## Dados Brutos
 
 ![image](https://user-images.githubusercontent.com/112008347/192047004-c52913f3-9759-433e-9a48-f61ff74d4d3e.png)
 
 ## Medidas [Formulas]
 
### Market Share
Faturamento = SUM('Market Share'[Faturamento])
Faturamento 2º Colocada = SUM('Market Share'[Faturamento_2_Colocada])
Variação Faturamento = DIVIDE([Faturamento 2º Colocada], [Faturamento]) - 1
 
 ### Lucratividade
 Lucro Liquido = CALCULATE(SUM(Indicadores[Valor]), Indicadores[Indicador] = "Lucro Liquido")
 Receita Total = CALCULATE(SUM(Indicadores[Valor]), Indicadores[Indicador] = "Receita Total")
 Lucratividade = DIVIDE([Lucro Liquido], [Receita Total])
 
 ### Churn Rate
 
Clientes Ativos = CALCULATE(SUM(Indicadores[Valor]), Indicadores[Indicador] = "Clientes Ativos")
Clientes Cancelados = CALCULATE(SUM(Indicadores[Valor]), Indicadores[Indicador] = "Clientes Cancelados")
Churn Rate = DIVIDE([Clientes Cancelados],[Clientes Ativos])

### Turnover Geral

Media Admissoes e Demissoes = CALCULATE(SUM(Indicadores[Valor]), Indicadores[Indicador] = "Media Admissoes e Demissoes ")
Colaboradores Ativos = CALCULATE(SUM(Indicadores[Valor]), Indicadores[Indicador] = "Colaboradores Ativos")
Turnover Geral = DIVIDE([Media Admissoes e Demissoes], [Colaboradores Ativos]

### NPS

NPS - Total Clientes Responderam = CALCULATE(SUM(Indicadores[Valor]), Indicadores[Indicador] = "NPS - Total Clientes Responderam ")
NPS - Total Clientes Promotores = CALCULATE(SUM(Indicadores[Valor]), Indicadores[Indicador] = "NPS - Total Clientes Promotore")
NPS - Total Clientes Detratores = CALCULATE(SUM(Indicadores[Valor]), Indicadores[Indicador] = "NPS - Total Clientes Detratores ")
NPS = (DIVIDE([NPS - Total Clientes Promotores], [NPS - Total Clientes Responderam]) - DIVIDE([NPS -
Total Clientes Detratores], [NPS - Total Clientes Responderam])) * 100

### CSAT

CSAT - Total Clientes Responderam = CALCULATE(SUM(Indicadores[Valor]), Indicadores[Indicador] = "CSAT - Total Clientes Responderam ")
CSAT - Total Clientes Satisfeitos = CALCULATE(SUM(Indicadores[Valor]), Indicadores[Indicador] = "CSAT - Total Clientes Satisfeitos ")
CSAT = DIVIDE([CSAT - Total Clientes Satisfeitos], [CSAT - Total Clientes Responderam])

# DASHBOARD

![image](https://user-images.githubusercontent.com/112008347/192049366-7b31b86a-115b-4810-ab9a-f0c74ca416d0.png)

# ANALISES IMPORTANTES 

A região Sul tem os piores Índices de Qualidadeapesar de apresentar um Turnover Geral dentro da Meta;

- A região Sudeste precisa melhorar o Turnover Geral;

- As regiões Sul e Nordeste estão abaixo da meta de Lucratividade;

- A região Sul apresenta um Churn Rate próximo do limite.

# AÇÕES

Rever o processo de Treinamento dos Colaboradores na região Sul e analisar os atendimentos ruins;

- Analisar os casos de Demissão Passiva e Ativa na Região Sudeste para melhorar o Índice de Turnover Geral;

- Rever os Contratos das Regiões Sul e Nordeste para entender e melhorar a Lucratividade;

- Analisar os casos de Cancelamento da Região Sul para melhorar o Churn Rate.

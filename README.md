# bruna_fontes_160160162
problema 1- substituir nota do laboratório.

Problema 1 - Substituir nota do Laboratório.

Problema 1: Uma instalação de bombeamento tem apresentado problemas em uma seção de tubulação de 1 metro de comprimento e 40 mm de diâmetro. A perda de carga foi medida usando sensores de pressão, e mensurou-se uma queda de pressão de 2 Pa. A bomba que supre esta tubulação com água está operando em potência máxima. Também mediu-se a vazão deste escoamento, obtendo um valor de 0,0001 metro cúbico por segundo na saída do tubo. O projeto de CFD deve:

- Determinar se estes valores de vazão e perda de carga estão coerentes ou não, e o motivo para isto.
- Apresentar possibilidades de problemas em caso dos valores colocados acima não estarem coerentes.
- Usando a simulação apresentada, realizar um estudo paramétrico da velocidade máxima deste escoamento para avaliar se o cenário acima é normal ou não para esta instalação.


## 1. Modelagem

### 1.1 Objetivo
  A tecnologia computacional que permite realizar o estudo numérico de processos fluidodinâmicos, chamada de CFD, será usada no presente projeto, a fim de, realizar um estudo do escoamento da água, na tubulação de um bombeamento. Para a realização do estudo a ferramenta de simulação Ansys Fluent será utilizada. Tal ferramenta auxiliará na avaliação possíveis problemas, modificações caso não haja coerência dos resultados, e implementação de otimizações.
  
  ### 1.2 Requisitos de Solução
  O projeto deve apresentar um estudo paramétrico da velocidade máxima do escoamento na configuração fornecida, além de avaliar a coerência dos valores de vazão volumétrica e perda de carga fornecidos pelo problema. Possibilitando a comparação da análise teórica com a análise experimental em CFD, avaliando a necessidade de otimizações
  
  ### 1.3 Finalidade do Projeto
  O projeto possui finalidade acadêmica, ou seja, prevê o auxílio à disciplina de Dinâmica dos fluidos, por meio do estudo da Fluidodinâmica Computacional (CFD), muito utilizado na academia e na indústria atual. Tal ferramenta possibilita o aumento da eficiência, da segurança de processos, além da redução dos custos de produção.
  
  ### 1.4 Hipótese de Simplificações 
  A fim de facilitar o estudo do escoamento em dutos, podem ser adotadas hipóteses que simplificam a análise do cenário. Nesse projeto, serão adoadas as seguintes hipóteses para facilitar o estudo:
         - Escoamento Laminar;
         - Escoamento incompressível;
         - Rugosidade do material do duto desprezíve.
  Caso os resultados da simulução não sejam coerentes com os resultados experimentais, a simplificação quanto rugosidade do material poderá ser desconsiderada. 
  
  ### 1.5 Precisão dos Resultados 
  Para simulações numéricas em CFD é de extrema importância avaliar a precisão dos cálculos, pois influenciará diretamente na simulação podendo até impedir sua convergência, afetando os resultados. A fim de obter resultados fiéis ao problema estudado, condições de contorno necessitam ser bem definidas. Deve-se, também, adequar a simulação ao meio acadêmico o aumento no número de elementos de malha será aplicado para uma maior precisão dos resultados, além de ajustar os resíduos que indicam nível de convergência em 10^-4. 
  
  ### 1.6 Metodologia
  A melhor metodologia a ser aplicada nesse caso é o estudo CFD pois permite um processo iterativo, com mudanças ágeis, além de possuir baixo custo. Baseado nisso, para a realização da modelagem, pré-proccessamento, processamento e pós-processamento será utilizado software comercial ANSYS R19.2, e para a análise do sistema será adotado o método Fluent.
  
  ### 1.7 Prazo de Entrega
   O projeto é em três etapas, sendo elas: Modelagem; Pré-Processamento e Processamento. Considerando que cada etapa dure uma semana, a duração prevista do projeto é de três semanas a um mês. No entanto, o prazo é admite alterações, visto que, serão dados feedbacks pelo professor após a conclusão de cada etapa. 
    
 ### Geometria 
 
 A geometria apresentada abaixo representa a região do escoamento do fluido.
 
<p align="center">
  <img width="450" height="250" src="https://github.com/Dinamica-dos-Fluidos-CFD/bruna_fontes_160160162/blob/master/problem_1_vistaiso.jpg">
</p>
<p align="center">
  <b>Figura 1- Vista Isométrica da geometria</b>
</p>

<p align="center">
  <img width="450" height="250" src="https://github.com/Dinamica-dos-Fluidos-CFD/bruna_fontes_160160162/blob/master/problem1_vistal_lateral.jpg">
</p>
<p align="center">
  <b>Figura 2- Vista lateral da geometria</b>
</p>

<p align="center">
  <img width="450" height="250" src="https://github.com/Dinamica-dos-Fluidos-CFD/bruna_fontes_160160162/blob/master/problem_1_vistafrontal.jpg">
</p>
<p align="center">
  <b>Figura 3- Vista frontal da geometria</b>
</p>


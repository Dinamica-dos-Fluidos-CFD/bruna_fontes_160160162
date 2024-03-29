## Desafio Aorta

### Geometria 

O desafio compreende a simulação do escoamento do sangue em uma aorta para validar o gradiente de pressão. A geometria fornecida pelo problema, requer um ajuste para fins de simplificação da simulação. Primeiramente, no SpaceClaim a geometria foram utilizadas 2 ferramentas para suavizar a geometria e diminuir o número de faces sendo elas: Reduce -> Shrinkwrap. Após sua simplificação, utilizou-se a ferramenta Facets para converter a geometria para sólido, além da ferramenta Merge faces que foi utilizada na entrada e saídas da aortas, eliminando diversas faces para facilitar a seleção no setup. 

<p align="center">
  <img width="550" height="370" src="https://github.com/Dinamica-dos-Fluidos-CFD/bruna_fontes_160160162/blob/master/geometria%20aorta.png">
</p>


## Malha 

A maior dificuldade da simulação consiste na geração de uma malha que atenda aos requisistos de qualidade, além de acordar com os recusos computacionais Disponíveis. Para tal, foram utilizados o seguintes metodos de geração: Virtual topology -> Patch conforming method. Ainda assim, pelos métodos utilizados, não foi possível obter um bom resultado de dissemetria. 

<p align="center">
  <img width="550" height="370" src="https://github.com/Dinamica-dos-Fluidos-CFD/bruna_fontes_160160162/blob/master/malha_aorta_1.png">
</p>

<p align="center">
  <img width="300" height="120" src="https://github.com/Dinamica-dos-Fluidos-CFD/bruna_fontes_160160162/blob/master/malha_aorta_2.png">
</p>

### Pré-processamento

Para o pré processamento não foi considerada o modelo transiente, nem efeitos visosos ou tranferência de calor. Para o escoamento, foi adotado o modelo de turbulência K-epsilon RNG, onde as equações de navier-stokes são normalizadas considerando efeitos de movimento menores, além de considerar baixos núumeros de Reynolds, sendo adequado para o sangue, visto, que é um fluido não newtoniano. O número de resíduos utilidados de foi de 10^-4, e o sangue foi modelado conforme a figura abaixo.


<p align="center">
  <img width="530" height="350" src="https://github.com/Dinamica-dos-Fluidos-CFD/bruna_fontes_160160162/blob/master/blood.png">
</p>


As condições de contorno para a entrada foi usado a velocidade de 0,35 m/s e pressão manométrica na entrada de 0 Pa, e na saída foi adotado a pressão manométrica de 1300 Pa. Tais configurações não resultaram resíduos de convergência satisfatório. E a simulação convergiu quando os resíduos atingiram valores a ordem de 10^-2.

<p align="center">
  <img width="570" height="350" src="https://github.com/Dinamica-dos-Fluidos-CFD/bruna_fontes_160160162/blob/master/residuo_aorta.png">
</p>
 

### Pós processamento

O gradiente de pressão estática mostrou a queda de pressão ao longo da aorta, tal comportamento condiz ao esperado para escoamentos internos. A pressão arterial média é de 120 mmHg (16 kPa) durante a fase sistólica, entretando a pressão média simulada resultou em de 1,79 kPa. Os resultados da simulação não foram satisfatórios devido aos recursos computacionais limitados, mas a simulação mostra coerência com fenomeno fisico em questão.


<p align="center">
  <img width="570" height="350" src="https://github.com/Dinamica-dos-Fluidos-CFD/bruna_fontes_160160162/blob/master/resultado_aorta.png">
</p>

### Conclusão 

 Devido aos recursos computacionais disponíveis a simulação apresentou valores destoando com a realidade, tal questão se deve a malha empregada no modelo 3D. Para bons resultados um estudo com malhas mais refinadas deve ser realizado. Por se tratar de uma simulação de alta complexidade bons rescursos computacionais são de extrema valia. Porém o problema estudado cumpriu com sua função de desafiar novas possibilidades da dinâmica dos fluidos para além dos estudos relacionados a engenharia. 
 




# bruna_fontes_160160162 TRABALHO ENCERRADO
problema 1- substituir nota do laboratório.

Problema 1 - Substituir nota do Laboratório.

Problema 1: Uma instalação de bombeamento tem apresentado problemas em uma seção de tubulação de 1 metro de comprimento e 40 mm de diâmetro. A perda de carga foi medida usando sensores de pressão, e mensurou-se uma queda de pressão de 2 Pa. A bomba que supre esta tubulação com água está operando em potência máxima. Também mediu-se a vazão deste escoamento, obtendo um valor de 0,0001 metro cúbico por segundo na saída do tubo. O projeto de CFD deve:

- Determinar se estes valores de vazão e perda de carga estão coerentes ou não, e o motivo para isto.
- Apresentar possibilidades de problemas em caso dos valores colocados acima não estarem coerentes.
- Usando a simulação apresentada, realizar um estudo paramétrico da velocidade máxima deste escoamento para avaliar se o cenário acima é normal ou não para esta instalação.


## 1. Modelagem

### 1.1 Objetivo
O objetivo geral do presente projeto é a análise do escoamento de um fluido na tubulação de um bombeamento, que apresenta 40 mm de diâmetro e 1 metro de comprimento, através da simulação numérica utilizando o software Ansys Fluent. Tal análise permitirá avaliar parâmetros do escoamento como: Vazão e a perda de carga. Bem como, possíveis problemas na instalação, implementação de otimizações, e modificações caso os resultados não apresentem coerência com os valores citados pelo problema.
  
  ### 1.2 Requisitos de Solução
O projeto tem como requisito apresentar um estudo quantitativo, comparando as simulações com os dados experimentais dados pelo problema, assim, analisando se os valores apresentados de perda de carga e vazão volumértica concordam entre si. Também, será realizado um estudo paramétrico baseado na velocidade máxima do escoamento na tubulação.
  
  ### 1.3 Finalidade do Projeto
  O projeto possui finalidade acadêmica, ou seja, prevê o auxílio à disciplina de Dinâmica dos fluidos, por meio do estudo da Fluidodinâmica Computacional (CFD), muito utilizado na academia e na indústria atual. Tal ferramenta possibilita o aumento da eficiência, da segurança de processos, além da redução dos custos de produção.
  
  ### 1.4 Hipótese de Simplificações 
  A fim de simplificar a modelagem do problema, auxiliar as definições das condições de contorno, e alcançar resultados precisos na análise do escoamento do fluido no duto, serão adotadas as seguintes hipóteses: 

 - Escoamento Laminar;
 
 - Escoamento incompressível;
 
 - Rugosidade do material do duto desprezível;
 
 - Tubulação não apresenta conexões.
 
 Caso os resultados da simulação não sejam coerentes com os resultados experimentais, algumas dessas simplificações poderão ser desconsideradas. 

  
  ### 1.5 Precisão dos Resultados 
  Para simulações numéricas em CFD é de extrema importância avaliar a precisão dos cálculos, pois influenciará diretamente na simulação podendo até impedir sua convergência, afetando os resultados. A fim de obter resultados fiéis ao problema estudado, condições de contorno necessitam ser bem definidas. Deve-se, também, adequar a simulação ao meio acadêmico o aumento no número de elementos de malha será aplicado para uma maior precisão dos resultados, além de ajustar os resíduos que indicam nível de convergência em 10^-4. 
  
  ### 1.6 Metodologia
  A melhor metodologia a ser aplicada nesse caso é o estudo CFD pois permite um processo iterativo, com mudanças ágeis, além de possuir baixo custo. Baseado nisso, para a realização da modelagem, pré-proccessamento, processamento e pós-processamento será utilizado software comercial ANSYS R19.2, e para a análise do sistema será adotado o método Fluent.
  
  ### 1.7 Prazo de Entrega
   O projeto é dividido em três etapas, sendo elas: Modelagem; Pré-Processamento e Processamento. Considerando que cada etapa dure uma semana, a duração prevista do projeto é de três semanas a um mês. No entanto, o prazo é admite alterações, visto que, serão dados feedbacks pelo professor após a conclusão de cada etapa. 
    
 ### Geometria 
 
 A geometria apresentada abaixo representa a região do escoamento do fluido.
 
<p align="center">
  <img width="470" height="300" src="https://github.com/Dinamica-dos-Fluidos-CFD/bruna_fontes_160160162/blob/master/problem_1_vistaiso.jpg">
</p>
<p align="center">
  <b>Figura 1- Vista Isométrica da geometria</b>
</p>



<p align="center">
  <img width="470" height="300" src="https://github.com/Dinamica-dos-Fluidos-CFD/bruna_fontes_160160162/blob/master/problem1_vistal_lateral.jpg">
</p>
<p align="center">
  <b>Figura 2- Vista lateral da geometria</b>
</p>


<p align="center">
  <img width="470" height="300" src="https://github.com/Dinamica-dos-Fluidos-CFD/bruna_fontes_160160162/blob/master/problem_1_vistafrontal.jpg">
</p>
<p align="center">
  <b>Figura 3- Vista frontal da geometria</b>
</p>


<p align="center">
  <img width="470" height="300" src="https://github.com/Dinamica-dos-Fluidos-CFD/bruna_fontes_160160162/blob/master/Inlet.png">
</p>
<p align="center">
  <b>Figura 4- Esquemático da geometria</b>
</p>

## 2. Pré-Processamento

### 2.1 Domínio e Geometria
No CFD o domínio representa a região a qual será feita o cálculo, essa região contínua é discretizada por uma malha que representa pequenos volumes de controle. A fim de facilitar o processamento é importante deixar a malha simplificada, livre de chanfros, curvaturas, desconsiderando elementos geométricos supérfluos para não haver regiões com excesso de elementos de malha desnecessários. Portanto esse processo é demorado e de extrema importância para garantir a aproximação do fenômeno físico. Para o projeto, o domínio do cálculo está sendo representado apenas pelo diâmetro interno da tubulação onde está ocorrendo o escoamento do fluido, tornando a geometria adequada para a simulação.

### 2.2 Malha
A qualidade da malha para estudo CFD é de extrema importância para obtenção de bons resultados. Devido à baixa complexidade do problema, e por apresentar uma geometria de domínio simples, será utilizada uma malha estruturada. Além disso, por se tratar de simulações CFD o método dos volumes finitos (FVM) é utilizado.

Para a abordagem inicial do problema, a malha foi gerada automaticamente pelo “Genarate mesh”, caso necessário, outros métodos serão utilizados.

<p align="center">
  <img width="470" height="300" src="https://github.com/Dinamica-dos-Fluidos-CFD/bruna_fontes_160160162/blob/master/generate_mesh.png">
</p>
<p align="center">
  <b>Figura 5 - Gerando malha automática</b>
</p>



<p align="center">
  <img width="470" height="300" src="https://github.com/Dinamica-dos-Fluidos-CFD/bruna_fontes_160160162/blob/master/malha_automatica.png">
</p>
<p align="center">
  <b>Figura 6 - Malha do Cálculo</b>
</p>


A fim de avaliar a qualidade da malha para a precisão dos resultados serão usados os parâmetros de Dissimetria e qualidade Ortogonal.

<p align="center">
  <img width="450" height="270" src="https://github.com/Dinamica-dos-Fluidos-CFD/bruna_fontes_160160162/blob/master/skewness_metric.png">
</p>
<p align="center">
  <b>Figura 7 - Métrica Dissimetria da malha</b>
</p>


<p align="center">
  <img width="450" height="270" src="https://github.com/Dinamica-dos-Fluidos-CFD/bruna_fontes_160160162/blob/master/ortogonal_metric.png">
</p>
<p align="center">
  <b>Figura 8 - Qualidade Ortogonal da malha</b>
</p>

Aqui, ainda são estabelecidas as regiões de contorno do problema (entrada e saída):

- Selecionar-se a face de interesse com o botão direito do mouse:

<p align="center">
  <img width="550" height="370" src="https://github.com/Dinamica-dos-Fluidos-CFD/bruna_fontes_160160162/blob/master/create_outlet.png">
</p>

- Não é necessário definir a região de parede, o Fluent automaticamente seleciona como parede as regiões do domínio que não foram selecionadas.
 



### 2.3 SETUP

Após feita a geração da malha é possível dar início ao setup do problema. Mas antes, é necessário estabelecer os parâmetros que serão inseridos nas condições de contornos. Essas informações do problema servirão de referência para inicializar a solução:

- Vazão volumétrica de saída: 0,0001 m³/s
- Pressão estática na saída: 0 Pa (pressão relativa)
- Velocidade na entrada: 0,0795 m/s

A velocidade na entrada foi calculada pela a vazão fornecida no problema através da equação da continuidade. 

![](https://github.com/Dinamica-dos-Fluidos-CFD/bruna_fontes_160160162/blob/master/eq_continuidade.gif)

![](https://github.com/Dinamica-dos-Fluidos-CFD/bruna_fontes_160160162/blob/master/vazao_2.gif)

Sendo,

![](https://github.com/Dinamica-dos-Fluidos-CFD/bruna_fontes_160160162/blob/master/area1.gif)

Assim,

![](https://github.com/Dinamica-dos-Fluidos-CFD/bruna_fontes_160160162/blob/master/vel_1.gif)


Definido os parametros é possível dar início ao SETUP do problema.

- Primeiramente, define-se o modelo do problema. Nessa área, é possível ativar todas as equações de transporte que deseja-se usar. No caso, será ativado o modelo da viscosidade (laminar), e também o da energia, afim de, especificar a temperatura do fluido no escoamento.
<p align="center">
  <img width="550" height="370" src="https://github.com/Dinamica-dos-Fluidos-CFD/bruna_fontes_160160162/blob/master/models.png">
</p>

- Definir água como o fluido de trabalho com as condições de acordo com a temperatura de 25 °C:

<p align="center">
  <img width="620" height="340" src="https://github.com/Dinamica-dos-Fluidos-CFD/bruna_fontes_160160162/blob/master/material.png">
</p>

- Definir as condições de contorno
  
  **#Input 1:Velocidade do escoamento**

A velocidade de 0,0795 m/s calculada acima é um dos parâmetros de entrada. 
  
  <p align="center">
  <img width="650" height="340" src="https://github.com/Dinamica-dos-Fluidos-CFD/bruna_fontes_160160162/blob/master/inlet_velocidade.png">
</p>

**#Input 2: Pressão na saída**

Por último, a pressão na saída de 0 Pa foi determinada com o intuito de facilitar o cálculo da perda de carga. Assim, o valor da pressão na entrada calculado na simulação, será a queda de pressão.

 <p align="center">
  <img width="650" height="340" src="https://github.com/Dinamica-dos-Fluidos-CFD/bruna_fontes_160160162/blob/master/Outlet_pressure.png">
</p>


- Definir método de solução: No presente caso, está sendo utilizado o padrão do FLUENT

<p align="center">
<img width="500" height="340" src="https://github.com/Dinamica-dos-Fluidos-CFD/bruna_fontes_160160162/blob/master/metodos_solucao.png">
</p>

- Definir resíduos para controlar a convergência do caso: Aqui está sendo adotado o erro residual de 10^-4


<p align="center">
<img width="560" height="340" src="https://github.com/Dinamica-dos-Fluidos-CFD/bruna_fontes_160160162/blob/master/residuo.png">
</p>

- Definir o número de itereções para iniciar a simulação:

<p align="center">
<img width="520" height="340" src="https://github.com/Dinamica-dos-Fluidos-CFD/bruna_fontes_160160162/blob/master/calculation.png">
</p>


### Recursos Computacionais
Os recursos computacionais disponíveis para a realização da simulação encontram-se abaixo:

|Item               |Especificações              |
|-------------------|----------------------------|
|Sistema Operacional|Microsoft Windows 10 Home   |
|Processador        |Intel Core i5-6200U 2.30GHz |
|Memória RAM        |8GB                         |

Por fim, de acordo com os recursos computacionais, é previsto que o processamento seja realizado em um período de uma semana e que, após revisões, a etapa de pré-processamento e processamento seja concluída em um total de duas semanas.


## 3. Processamento e Pós-Processamento Laminar


### 3.1 Convergência 

Primeiramente, foi definido o critério de convergência residual de 1e-4, obtendo a convergência com  880 iterações em 1 minuto e 15 segundos. E depois, a fim de analisar alguma melhora nos resultados,  foi adotado o critério de convergência residual de 1e-6, o qual convergiu a 980 iterações em 1 minuto e 28 segundos. De qualquer forma, ambos apresentaram um histórico de convergência dos resultados adequado.

<p align="center">
  <img width="470" height="300" src="https://github.com/Dinamica-dos-Fluidos-CFD/bruna_fontes_160160162/blob/master/residuo_4.jpg">
</p> <p align="center">
  <b> Figura 9 - Convergência residual a 1e-4 </b>
  </p>


<p align="center">
  <img width="470" height="300" src="https://github.com/Dinamica-dos-Fluidos-CFD/bruna_fontes_160160162/blob/master/residuo_6.jpg">
</p> 
<p align="center">
 <b> Figura 10 - Convergência residual a 1e-6 </b>
  </p>
  
  
  ### 3.3 Resultados e Discussão 
  
  
  <p align="center">
  <img width="500" height="300" src="https://github.com/Dinamica-dos-Fluidos-CFD/bruna_fontes_160160162/blob/master/quedapressao.jpg">
</p> 
<p align="center">
  <b>Figura 11 - gradiente de pressão</b>
</p>

 <p align="center">
  <img width="500" height="300" src="https://github.com/Dinamica-dos-Fluidos-CFD/bruna_fontes_160160162/blob/master/perdadecargal.png">
</p> 
<p align="center">
  <b>Figura 12 - Perda de Carga</b>
</p>

Afim de validar os resultados da queda de pressão fornecido pela simulação serão realizados os seguintes cálculos teóricos:

  **# Número de Reynolds**
  
  ![](https://github.com/Dinamica-dos-Fluidos-CFD/bruna_fontes_160160162/blob/master/reynolds.gif)  (1)
  
  Sendo,
  
  ![](https://github.com/Dinamica-dos-Fluidos-CFD/bruna_fontes_160160162/blob/master/visc_din_agua_25.gif)
  
  ![](https://github.com/Dinamica-dos-Fluidos-CFD/bruna_fontes_160160162/blob/master/massa_esp_agua_25.gif)
  
  Então,
  
  ![](https://github.com/Dinamica-dos-Fluidos-CFD/bruna_fontes_160160162/blob/master/reynolds_result.gif)
  
 
  **# Perda de Carga**
  
 Para o cálculo da perda de carga deve ser calculado o fator de atrito
 
 ![](https://github.com/Dinamica-dos-Fluidos-CFD/bruna_fontes_160160162/blob/master/fator_atrito_laminar.gif) (2)
 
 Assim, 
 
 ![](https://github.com/Dinamica-dos-Fluidos-CFD/bruna_fontes_160160162/blob/master/queda_pressao_laminar.gif) (3)
 
 Previamente, pelo número de Reynolds calculado acima, o escoamento seria considerado em transição de acordo com a teoria. Contudo, devido as considerações feitas na modelagem do problema, foi considerado ainda o modelo laminar para a análise dos resultados. Dessa forma, é confirmado que os resultados no Fluent não demostrem a realidade do problema, visto que, numericamente o modelo laminar não capturaria os efeitos turbulentos do escoamento. De qualquer forma, é possível ver que a queda de pressão consiste com a teoria do escoamento viscoso, visto que o contato com a parede da tubulação faz com que ocorra a queda da pressão linearmente como mostrado na **Figura 12**.

 
 
|Perda de Carga   | (Pa)               |
|-----------------|--------------------|
| Fornecida       |    2.0             |
| Teórica Laminar |    1.34            |
| Simulação       |    2.69            |
 

Dessa forma, é possível visualizar que os resultados teórico para o modelo laminar, e da simulação apresentam uma discordância igual a 100,75%. Sendo maior que a margem de erro aceitável de 10%.

Faz-se  necessário então analisar a velocidade do escoamento

 <p align="center">
  <img width="500" height="300" src="https://github.com/Dinamica-dos-Fluidos-CFD/bruna_fontes_160160162/blob/master/velocity.png">
</p> 
<p align="center">
  <b>Figura 13 - gradiente de velocidade</b>
</p>

  
  <p align="center">
  <img width="500" height="300" src="https://github.com/Dinamica-dos-Fluidos-CFD/bruna_fontes_160160162/blob/master/perfeilvel.png">
</p> 
<p align="center">
  <b>Figura 14- Perfil de Velocidade</b>
</p>

Analisando o gradiente de velocidade na **Figura 13** pode-se observar que o escoamento encontra-se plenamente desenvolvido antes da metade da tubulação. Já pelo perfil de velocidade da **Figura 14** é possível ver que o contato com o tubo faz com que a velocidade nas bordas seja retardada, e o escoamento na região cental acelerado para manter o requisito de continuidade incompressível. Observa-se que apesar da velocidade na região de contato é zero, mas não ocorre o formato parabólico como é esperado em um escoamento laminar. A figura abaixo mostra o perfil parabólico representativo do escoamento laminar 


 <p align="center">
  <img width="250" height="180" src="https://github.com/Dinamica-dos-Fluidos-CFD/bruna_fontes_160160162/blob/master/perfil%20laminar.png">
</p> 
<p align="center">
  <b>Figura 15- Perfil de Velocidade no escoamento laminar</b>
</p>

Na imagem abaixo é possível verificar que o perfil de velocidade do problema se assemelha ao perfil de um escoamento turbulento, onde os gradientes de velocidade na região da parede são maiores, e o gradiente mais baixo na região central, semelhante ao formato de um chapéu.

 <p align="center">
  <img width="300" height="180" src="https://github.com/Dinamica-dos-Fluidos-CFD/bruna_fontes_160160162/blob/master/perfil_turbulento.png">
</p> 
<p align="center">
  <b>Figura 16- Perfil de Velocidade no escoamento turbulento</b>
</p>

  
  ### Estudo Paramétrico
  
  Foi efetuado um estudo paramétrico a fim de validar os resultados da simulação com a teoria sobre o escoamento laminar. Aqui foram analisados a velocidade máxima do escoamento, a velocidade média e o comportamento da perda de carga da tubulação.
  
  Abaixo, o estudo paramétrico do problema:
<p align="center">
  <img width="500" height="300" src="https://github.com/Dinamica-dos-Fluidos-CFD/bruna_fontes_160160162/blob/master/estudo_parametrico_1.png">
</p> 
<p align="center">
  <b>Figura 17- Estudo paramétrico </b>
</p>
  


Para verificar o estudo da velocidade máxima no escoamento laminar, a relação abaixo deve ser satisfeita. Essa relação ocorre por consequencia do perfil parabólico do escoamento laminar visto na **Figura 15** 


![](https://github.com/Dinamica-dos-Fluidos-CFD/bruna_fontes_160160162/blob/master/eq_velocidade_maxima.gif) (4)


É possível verificar que a relação da velocidade máxima com a velocidade média não condiz com o equacionamento apresentado acima válido para o escoamento laminar, visto que a velocidade máxima em todas as variáveis não apresentou o dobro da velocidade média do escoamento. E Também, foi observado que a queda de pressão da tubulação só pode ser concordada com o valor fornecido no  problema (2 Pa) se houver a redução da velocidade média na tubulação. 

De acordo com a discussão exposta acima, e a teoria do escoamento laminar em tubos, pode-se pontuar os seguintes problemas:

- O resultado da perda de carga não condiz com o valor teórico laminar, e nem com o valor apresentado pelo problema, exceto, se houver redução na velocidade do escoamento;

- Há problemas na medição do equipamento ou estruturais na tubulação;

- O Perfil de velocidade apresentado não é parabólico como em um escoamento laminar;

- O número de Reynolds calculado indica que o escoamento encontra-se em transição.



Dessa maneira, conclui-se que o modelo laminar para o problema não é adequado, sendo necessário um novo processamento considerando o modelo em transição. 


## 4. Processamento e Pós-Processamento Turbulento 

Como citado anteriormente, o escoamento encontra-se na região de transição. Para tal, será adotado no processamentodo fluent o modelo de turbulência K-epsilon. Abaixo é possível ver a convergência residual de 1e-6 adotada anteriormente. 


<p align="center">
  <img width="470" height="300" src="https://github.com/Dinamica-dos-Fluidos-CFD/bruna_fontes_160160162/blob/master/residuo_turbulento.jpg">
</p> 
<p align="center">
 <b> Figura 17 - Convergência residual a 1e-6 </b>
  </p>
  
  
  ### 3.1 Resultados e Discussão 
  

Para o caso turbulento novos cálculos foram feitos. Para determinar o fator de atrito foi utilizado o Diagrama de Moody, usando como referência a linha que indica tubos lisos em conjunto com o número de reynolds calculado de aproximadamente 3500. Abaixo o fator de atrito:

![](https://github.com/Dinamica-dos-Fluidos-CFD/bruna_fontes_160160162/blob/master/fator_de_atrito.gif)

Já estabelecido o fator de atrito pode-se calcular a perda de carga:

![](https://github.com/Dinamica-dos-Fluidos-CFD/bruna_fontes_160160162/blob/master/perda_de_carga_turb.gif)


 <p align="center">
  <img width="500" height="300" src="https://github.com/Dinamica-dos-Fluidos-CFD/bruna_fontes_160160162/blob/master/pressao_turbulento.jpg">
</p> 
<p align="center">
  <b>Figura 18- Gradiente de pressão </b>
</p>


<p align="center">
  <img width="500" height="300" src="https://github.com/Dinamica-dos-Fluidos-CFD/bruna_fontes_160160162/blob/master/perda_de_carga_turb.png">
</p> 
<p align="center">
  <b>Figura 19- Perfil da Perda de Carga </b>
</p>

O resultado da queda de pressão de 3,40 Pa apresenta coerência, com uma diferencia do valor teórico de apenas 7,6% o que está dentro do erro percentual aceitado para um projeto CFD. O comportamento da queda de pressão também apresenta coerência com o esperado para escoamentos viscosos como dito anteriormente.


  <p align="center">
  <img width="500" height="300" src="https://github.com/Dinamica-dos-Fluidos-CFD/bruna_fontes_160160162/blob/master/velocidade_turbulento.jpg">
</p> 
<p align="center">
  <b>Figura 20- Gradiente de Velocidade</b>
</p>

<p align="center">
  <img width="500" height="300" src="https://github.com/Dinamica-dos-Fluidos-CFD/bruna_fontes_160160162/blob/master/perfil_vel_turb.png">
</p> 
<p align="center">
  <b>Figura 21- Perfil da Velocidade </b>
</p>


É possível ver pela figura **Figura 20** que a velocidade se desenvolve já no início da tubulação o que é esperado para um modelo turbulento. Dessa forma, é possível concluir que é correto utilizar o modelo turbulento em casos em que o escoamento apresentam o número de Reynolds maior que 2300.

## Conclusão

Conforme as análises anteriores utilizando o software Ansys Fluent para o estudo do escoamento de água em uma tubulação, é possível inferir que a simulação e o estudo paramétrico foram fundamentais para obtenção de resultados condizentes a realidade físico-teórico do problema, apontando  um possível erro relacionado as medições realizadas quando comparado a resultados analíticos e numéricos obtidos, expressando o quanto essa ferramenta é importante para a academia e a indústria. Pelo estudo da velocidade máxima, foi possível concluir a necessidade de usar o modelo de turbulencia em escoamentos em transição, e que a simplificação para o modelo laminar não contribuiria rigorosamente para resultados numéricos esperados pelo CFD.

Ademais, o erro experimental da perda de carga e da vazão apresentados, podem estar relacionados ao um erro instrumental, ou a mudança da geometria da tubulação, visto que, pela análise da equação da perda de carga, a mudança da geometria associada ao diâmetro contribuiria para a baixa variação de pressão exposto pelo problema. Assim, os objetivos gerais do projeto e seus requisitos propostos foram atendidos, mostrando como o CFD é uma ferramenta importante para estudos da engenharia.








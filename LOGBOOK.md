## Título do Projeto: Robo Trader em Python
Disciplina: Tópicos em Engenharia de Sistemas de Informação 3\
Alunos: Jean Carlos B. da Mata e Juliana do Nascimento Rocha\
Professor: Thyago Carvalho\
Período: 2025/2

## O que foi feito até agora:
*Estudo do caso\
O que ficou entendido?\
O que foi decidido?\

*Entendimento dos dados

Inicialmente Foram feitas análises por meio de gráficos com os atributos disponíveis na tabela do mini índice da b3, de 15 de outubro de 2020 à 19 de abril de 2023. No intuito de entender seu comportamento para em seguida estudar sobre o gap de abertura e os limites de suporte e resistência.

1 Preço e Média móvel

![Arquivo](https://drive.google.com/uc?export=view&id=1xjmZN667Dm74_LDH0nDd2p9J0HCi6VS4)

A linha azul representa o fechamento diário
A linha amarela uma média de curto prazo (20 dias)
A linha roxa uma média de longo prazo (50 dias)

Quando a linha azul está acima das outras indica um otimismo do mercado\
Linha amarela e azul abaixo da roxa indica um mercado pessimista\
Quando estão próximas indica indecisão\

2 Volatilidade diária 

![Arquivo](https://drive.google.com/uc?export=view&id=1ewUyH6VhxvdK54L0D6BwiNt4KsSGpsvg)

Esse gráfico mostra a variação entre o maior e menor valor do preço por dia e a linha vermelha seria a volatilidade esperada desse ativo

normalmente dias com uma porcentagem alta indicam um risco maior por serem mais imprevisíveis (como no final de 2022)

3 Volume e Spread

![Arquivo](https://drive.google.com/uc?export=view&id=1RI1RGPl_-HYglmHFV6HaMcizHX_Iw7-y)

A linha azul representa o TickVol, número de negócios ou
transações que ocorreram no período.
A vermelha o Spread, diferença do preço de compra e
venda num determinado momento.

Pela teoria quanto maior a linha azul, menor será
a linha vermelha
Pelo gráfico, o spread se mantém quase sempre em 5
e quedas bruscas para o zero,
possivelmente um erro na coleta do dados
Então não usaremos o Spread para nenhuma análise

4 Distribuição de Retornos diários

![Arquivo](https://drive.google.com/uc?export=view&id=1mvNk5CGAQufzD-UBvk729ol678c533si)

A maioria dos dias termina com uma variação de preço muito pequena
Em todo o tempo analisado do ativo, sua média é ligeiramente positiva, o que indica uma pequena valorização
Entretanto, há uma leve assimetria negativa, significa que há um risco de um dia de perda muito grande e repentina acontecer
O gráfico apresenta uma curtose alta, indicando mais momentos de calmaria e tem um risco mais do que comum de sofrer movimentos de preço muito grandes e súbitos.

5 Distribuição de Volatilidade

![Arquivo](https://drive.google.com/uc?export=view&id=1q-lGgYZRkxYT7_ocqxWdgwaDZX7RvPFG)

Há uma maior volatilidade perto da hora de fechamento

6 Distribuição de volume por hora do dia 

![Arquivo](https://drive.google.com/uc?export=view&id=1TaMHKKkTxticGQRI4IXnMb3Cj03jg5JM)

Há maiores volumes na abertura

O que os dados dizem?\
Como chegaram a essa conclusão?\
*Criação do dataset\
Os datasets criados estão no folder Datsets, sendo que a ordem de criação foi: 
  * Dataset_final_processado (variáveis sugeridas pelo Jean) e diarios (variáveis sugeridas pela Juliana). Os datasets foram criados ao mesmo tempo de pois válidados. Com base nas matrizes de confusão e nas análises de importância de features foi decidido juntar os dois datasets, uma vez que o do Jean apresentou bom desempenho com os verdadeiros negativos e o da Juliana apresentou bom desempenho com os verdadeiros positivos.
  * Em seguida foi criado o dataset_final processado juntando os dois datasets.
  * Por fim foi criado o dataset_pronto_para_modelo, com base no anterior, mas normalizado.

Durante a apresentação do modelo final, o professor sugeriu a retirada do feature media_diaria, por estarmos "prevendo" o futuro. A feature foi retirada do teste do simulador, mas decidmos mantê-la para criar um modelo que, com base na volatiliade dos últmos 90 minutos do dia anterior e com base nas médias diárias que possuimos, tente prever qual é o melhor horário de venda e de compra com base na média diária prevista.



## O que falta fazer:
*Validação do dataset com modelos lineares\
  *Seguindo as sugestões do professor, faremos a validação dos dois datasets, uma para verdadeiros positivos e um para verdadeiros negativos a fim de conseguir maior acurácia nas decisões do simulador.
  
*Criação do modelo do robô\
  Os simuladores de robô foram criados com os seguintes modelos:
    *Regrssão logística
    * Random forest
    *XGBost
    *Support Vector
  Testaremos o DBscan, que foi sugestão do professor.
*Simulação com o modelo\
*Teste com dados atualizados do mercado

## Problemas e dificuldades:

## Decisões tomadas:

## Próximos passos: 

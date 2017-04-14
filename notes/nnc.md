
# NNC

Bom dia pessoal,

Este aqui será o espaço para relatar todas as minhas atividades no Núcleo de Neurociências (NNC) da UFMG. 
A ideia é que todos possam utilizar desse espaço também, independente de sua área de formação. Então tentarei ser o mais simples possível.
Pra quem não entender nada sobre alguns termos, no final de cada tópico vou colocar umas sugestoezinhas legais para ler. 

****

Bom, estou trabalhando na análise dos dados que o Professor Cleiton coletou nos States. 
O nosso objetivo é estudar os processos de memória a um nível de sistemas, pensando, por exemplo, na influência da atividade do hipocampo sobre oscilações do córtex. Buscando isso, foram implantados eletrodos de estímulos na região CA1 do hipocampo de ratos, sendo os sinais de LFP registrados no córtex pré-frontal medial. Os sinais foram amostrados a nada menos que 30 KHz (pense em 30.000 amostras por segundo).

A estimulação elétrica induziu ondas delta. Então, realizar a detecção dessas ondas evocadas foi uma das minhas primeiras missões. O procedimento foi o seguinte:

\1. Os dados foram decimados (a taxa de amostragem foi reduzida por um fator de 15, no caso) -> Com uma taxa de amostragem de 30 KHz, seria quase uma missão impossível processar toda essa quantidade de dados. Eis aqui uma comparação entre o dado bruto e o dado decimado.

<p align="center">
  <img src="https://github.com/giuliazc/Open-Lab-Book/blob/master/notes/imagens/DadoBruto_Decimado.png" width="550"/>
</p>

Observe que isolamos janelas de 300 ms imediatamente após a aplicação de cada pulso elétrico. Esse é o intervalo de tempo suficiente para a análise das ondas delta evocadas. Para outras análises, variamos o tamanho das janelas. <br>
No experimento, foram aplicados pulsos elétricos a cada 20 s. Isso constituiu a chamada linha de base, com 15 min de duração. Guarde esse nome, pois vamos precisar dele. Depois foram aplicados estímulos de alta frequência (HFS - \*High frequency stimulation\*).

\2. Em seguida, os dados foram filtrados e normalizados (foram calculados os valores do escore-Z). O escore-Z basicamente representa o quanto uma medida se afasta da média em termos de desvios padrão. Os dados são centralizados para ter média 0. Se Z > 0, significa que o dado está acima da média. Se Z < 0, abaixo da média.<br> 
Para ter uma ideia melhor, observem esta imagem:

<p align="center">
  <img src="https://github.com/giuliazc/Open-Lab-Book/blob/master/notes/imagens/ZScore.png" width="550"/>
</p>

Para os dados com média ![equation](http://latex.codecogs.com/gif.latex?\bar{X}) e desvio padrão S, o escore-Z de um dado ponto x é calculado da seguinte maneira: <br>
![equation](http://latex.codecogs.com/gif.latex?X%3D%5Cfrac%7Bx-\bar{X}%7D%7BS%7D)

Aqui dá pra ver o que foi falado lá em cima: quando o valor em um ponto é igual à média dos dados, Z=0. 

\3. Dos escores-Z padronizados, obtive os cruzamentos em zero. Assim, de acordo com a duração entre dois cruzamentos sucessivos e da amplitude do sinal, foi detectada as ondinhas delta. No final, foi realizado um ajuste manual para os casos de falso positivo/falso negativo. Um exemplo do Ajuste Manual realizado está aqui:
<p align="center">
  <img src="https://github.com/giuliazc/Open-Lab-Book/blob/master/notes/imagens/AjusteManual.png" width="550"/>
</p>

Já já irei disponibilizar todos os códigos aqui. É só digitar, na linha de comando do MATLAB, 1, caso concorde com a classificação; ou 0, caso contrário. Coloquei um exemplo de uma onda Delta típica, para ficar mais fácil a classificação.

****

[Retornar ao índice ](https://github.com/giuliazc/Open-Lab-Book/blob/master/README.md)

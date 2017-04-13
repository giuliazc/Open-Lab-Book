
# NNC

Bom dia pessoal,

Este aqui será o espaço para relatar todas as minhas atividades no Núcleo de Neurociências (NNC) da UFMG. 
A ideia é que todos possam utilizar desse espaço também, independente de sua área de formação. Então tentarei ser o mais simples possível.
Pra quem não entender bulhufas sobre alguns termos, no final de cada tópico vou colocar umas sugestoezinhas legais para ler. 

****

Bom, estou trabalhando na análise dos dados que o Professor Cleiton coletou nos States. 
O nosso objetivo é estudar os processos de memória a um nível de sistemas, pensando, por exemplo, na influência da atividade do hipocampo sobre oscilações do córtex. Buscando isso, foram implantados eletrodos de estímulos na região CA1 do hipocampo de ratos, sendo os sinais de LFP registrados no córtex pré-frontal medial. Os sinais foram amostrados a nada menos que 30 KHz (pense em 30.000 amostras por segundo).

A estimulação elétrica induziu ondas delta. Então realizar a detecção dessas ondas evocadas foi uma das minhas primeiras missões. O procedimento foi o seguinte:

1) Os dados foram decimados (a taxa de amostragem foi reduzida por um fator de 15, no caso) -> Com uma taxa de amostragem de 30 KHz, seria quase uma missão impossível processar toda essa quantidade de dados.

****

[Retornar ao índice ](https://github.com/giuliazc/Open-Lab-Book/blob/master/README.md)

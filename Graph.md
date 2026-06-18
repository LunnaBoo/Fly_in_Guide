Os grafos deste projetos serão todos **grafos bidirecionais e com peso**, em inglês **undirected weighted graphs**. É importante que você se lembre disso muito bem daqui em diante. \
Um grafo bidirecional, undirected, é um grafo onde suas conexões, edges, não tem direção única. Pra gente, significa que se um Drone seguiu pela conexão entre a zona A e zona B ele pode **fazer o caminho de volta** para zona A usando a mesma conexão. \
Já um grafo com peso, weighted, é um grafo onde as conexões são associadas com **valores**, um **custo**. Um exemplo bom exemplo é pensar num GPS onde temos uma rota mais curta até o objetivo, porém congestionada, e outra mais longa, mas sem tráfego. \
Apesar da rota mais curta ser mais curta, pode ser que a mais longa ainda assim seja mais rápida. Ou seja, o **custo** associado a rota mais curta é **maior** do que o custo da mais longa. \
Os dois se aplicam aos grafos deste projeto, todos serão bidimensionais e com custo, já que podemos ir e voltar por uma mesma conexão e as conexões tem peso, como uma conexão para zona restrita, e por aí vai. 

A forma que escolhi para armazenar os dados relacionados ao grafo foi criando uma classe Graph. Essa classe irá armazenar:
1. hubs: list[Zone] | None = None
2. connections: list[Connection] | None = None
3. nb_drones: int = 0
4. start_hub: Zone | None = None
5. end_hub: Zone | None = None

Isso está no meu __init__. A razão pela qual iniciei tudo como None é que preferi que o __init__ não recebesse parâmetros. Ao invés disso, criei um método configure() que, esse sim, recebe por parâmetro os dados do map file, já tratados pelo Parser. \
A partir disso, esse método popula todos os atributos do __init__, chama um método auxiliar de validação extra, e então, iterando por todas os objetos Zone/hub e objetos Connection, adiciona todas as respectivas Connections as Zones/hubs. \
Essa última parte é importante porque facilita muito as coisas ter um atributo Connections em cada objeto Zona/hub que contenha todas as conexões relevantes para aquele hub, ou em outras palavras, todas conexões que mencionem aquele hub.
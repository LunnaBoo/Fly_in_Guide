Teremos uma classe Drone que representará os drones que atravessarão o mapa. Esta classe terá um atributo **de classe** para manter numa lista todas as instâncias de objetos da classe Drone. \
Já os atributos da instância serão:
1. id: String, "D" + len() da lista com todas as instâncias existentes da própria classe Drone + 1.
2. path: Lista de Zone | Connection, começa apenas com start_hub dentro.
3. route: Lista de Zone | float, inicialmente vazia.
4. dist: float, iniciado como float("inf").
5. finished_traversal: bool, iniciado como False.

Na última linha do __init__ adicione Drone._all_drones.append(self) (considerando que o nome da lista contendo todos os objetos drone seja chamada _all_drones. Caso não seja, mude o código de acordo). \
Essa linha é o que adicionará a instância na lista que definimos ANTES do __init__ como um atributo de classe. 

Agora precisamos implementar todos os métodos necessários para fazer com que o drone se mova. A forma que escolhi para fazer isso é ter 1 método act() que chama o método path_finding() e o método move(). \
O método act() é o que será chamado na minha classe Simulation, que será responsável por gerenciar os turnos. Nela, iremos iterar por todos os drones e chamar seu método act(). Assim, todos os drones irão agir 1 vez e o turno será completo.

No act(), nós iremos definir uma rota, caso ainda não sido definida, usando o método de path_finding(). Então, iremos chamar o método move() para de fato mover o drone de um hub para o outro. \
Caso o movimento não seja possível, em casos onde o próximo hub na rota esteja cheio e entre outros motivos, move()
retornará uma string vazia, que então será retornada por act(). \
Caso o movimento aconteça, move() irá retornar uma string contendo o movimento feito no formato '[ID do drone] - [Hub que entrou]', que então será retornado por act().

O método move() é responsável por checar se o movimento para o próximo hub na rota é possível ou não, e realiza-lo caso seja. Com realiza-lo quero dizer tirar o drone do hub em que estava e então coloca-lo no hub que entrou. Lembrando que em caso de conexões para zonas restritas o drone entrará numa conexão, e não num hub.

Já o método path_finding() é responsável por implementar o algoritmo de path-finding. Ele deve retornar uma tupla com dist, a distância entre start e goal em relação a rota escolhida, e route, a rota definida como a mais curta.

Minha recomendação para o algoritmo de path-finding é Djikstra, mas caso queira um desafio siga com A*, apesar de ser overkill. O Djikstra é o bastante para ter sucesso em todos os mapas, incluindo o challenger map.



https://towardsdev.com/dijkstras-algorithm-explained-the-heart-of-pathfinding-and-optimization-24d927b8adb5
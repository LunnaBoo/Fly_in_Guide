A classe Simulation é a responsável por gerenciar a simulação por turnos. Seu __init__ precisa ter:
1. graph: Graph | None = None
2. all_drones: list[Drone] = []
3. drones: list[Drone] = []
4. output: str = ""
5. finished: bool = False

Assim como na classe Graph, optei por ter um __init__ que não recebe nada por parâmetro, mas usar um método configure() para popular os atributos e configurar a classe. \
O método configure() recebe por parâmetro filename: str, que deve ser o nome do map file, para que então o método
possa chamar o MapParser.parse_data(filename), método principal do MapParser, e extrair todos os dados relevantes
para simulação. \
Com esses dados, iremos popular os atributos do __init__, instânciar um objeto da classe Graph e rodar seu método configure(). Por último, instânciamos objetos da classe Drone em número equivalente ao nb_drones, adicionamos todos em self.drones e copiamos self.drones para self.all_drones. \
O motivo para ter 2 atributos de lista de drones é porque durante a simulação eu removo drones da lista self.drones. Então, para não perder referencia destes drones removidos, o atributo all_drones se faz necessário. Caso seu programa não funcione desta forma, ajuste minhas instruções de acordo. \
O método configure() PRECISA ser executado antes de qualquer outro, faça validações nos outros métodos para ter certeza de que a classe foi previamente configurada.

Teremos também o método next_turn(), que será responsável por executar 1 turno da simulação. Ele irá iterar por todos os drones e chamar seus métodos act(). Assim, cada drone age uma vez. \
Além disso, também precisa checar por drones que tenham terminado a travessia, para que parem de ser contabilizados, não ajam, e coletar os outputs, as strings, retornadas pelos movimentos de cada drone. \
Ao juntar o output total do turno, irá adiciona-lo em self.output, que irá armazenar o output da simulação inteira, e chamar um método auxiliar para escrever o self.output em um arquivo outputs.txt. Não é necessário escrever num arquivo, mas eu gosto dessa abordagem.

Por último, o método restart_simulation(), que será responsável por reiniciar a simulação. Caso o usuário queira começar a simulação do zero, é melhor ter um método que faça isso do que esperar que o usuário feche e abra novamente o programa.
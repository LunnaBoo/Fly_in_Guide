# Zone/Hubs
Classe responsável por representar os Hubs em nossa simulação. Esta classe terá um atributo de classe para manter numa lista todas as instâncias de objetos Zone/Hub. 

Atributos serão:
- name: str
- kind: str
- pos: tuple[int, int]
- connections: list[Connection] = []
- is_start: bool = False
- is_end: bool = False
- max_drones: int = 1
- color: str | None = None
- weight: float = 1
- drones_in: list = []

Ao final do __init__, redefina o weight com base no self.kind, no tipo da Zona/Hub. Hubs Normais tem peso 1, Restritos peso 2, Prioritários peso 0.5 e Bloqueados tem peso float("inf"). Isso será de suma importância para o algoritmo de path-finding que virá a ser implementado.

Na última linha do init adicione Zone._all_zones.append(self) (considerando que o nome da lista contendo todos os objetos Zone/Hub seja chamada _all_zones. Caso não seja, mude o código de acordo).
Essa linha é o que adicionará a instância atual na lista que definimos ANTES do init como um atributo de classe.

# Connection
Classe que representará as conexões em nossa simulação. Esta classe terá um atributo de classe para manter numa lista todas as instâncias de objetos Connection. 

Atributos serão:
- name: str
- previous_zone: Zone
- next_zone: Zone
- max_link_capacity: int = 1
- drones_in: list = []

Na última linha do init adicione Connection._all_connections.append(self) (considerando que o nome da lista contendo todos os objetos Connection seja chamada _all_connections. Caso não seja, mude o código de acordo).
Essa linha é o que adicionará a instância atual na lista que definimos ANTES do init como um atributo de classe.
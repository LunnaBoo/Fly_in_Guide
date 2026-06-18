Primeiro precisamos definir como transferir os dados do map file para o código.

Temos:
1. Número de drones
2. start_hub
3. end_hub
4. Todas zonas do tipo hub
5. Todas as conexões entre zonas

A fomatação das zonas é:
- <zone_type>: <zone_name> <x> <y> <[optional metadata]>

Já a formatação das conexões é:
- <zone_type>: <zone_name>-<zone_name> <[optional metadata]>
Onde zone_type será sempre connection.

Todas essas informações vem em formato de KEY=VALUE pairs, o que significa que, a princípio, coloca-las num dicionário faz sentido.

Após colocar tudo em dicionário, precisaremos organizar os valores de cada coisa. \

Os hubs precisam se tornar objetos da classe Zone/hub, passando por atributo a coordenada e nome de cada um. Também é importante ter um True or False para marcar se a zona é start_hub ou end_hub. 

Já as conexões precisam entrar nos atributos de cada objeto Zone/hub, mas isso não será feito agora, e sim na classe Graph. Por enquanto, basta criar os objetos Connection para cada conexão.

Nosso retorno da parse_data:
dicionario: { \
  "nb_drones": int \
  "start_hub": Zone \
  "end_hub":   Zone \
  "hub: Zone \ 
  "connection": Connection \
}

Uma pergunta que pode aparecer é: Se temos múltiplos hubs e connections, então por que a chave "hub" e "connection" são singulares, guardam apenas 1 único hub e 1 única connection? \
A resposta pra isso é que há uma maneira de armazenar todos os Zones/hubs em uma única instância, e o mesmo vale para as Connections. Caso isso pareça confuso, vá para a pagina [[Zone Hubs e Connections]]. \
Dessa forma, podemos acessar uma lista com todas as zonas, e uma lista com todas as conexões, a partir de qualquer objeto zone.

Creio que essa seja a coisa mais relevante que posso dizer a respeito do Parser. Crie os objetos Zone/Hub e Connection aqui mesmo e utilize dessa técnica que citei para facilitar sua vida. De resto, é tão tedioso quanto qualquer outro Parser...
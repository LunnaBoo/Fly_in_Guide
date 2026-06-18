A visualização pode ser feita de diversas formas, mas, de acordo com o subject, apenas um print do output.txt em letras coloridas não é o bastante para contar como visualização. Dito isso, existem duas opções:
1. Printar no terminal com ANSI Code, poréḿ de maneira decente como no projeto anterior, A-Maze-ing.
2. Usar uma biblioteca externa para auxiliar no desenvolvimento de uma interface gráfica.

Tentei seguir com a primeira opção, mas percebi que é difícil printar um grafo tão complexo no terminal e ainda mais difícil simular movimento de 10, 20, 30 drones o atravessando. \
Por isso, segui com a segunda opção, e é minha recomendação para todos. O problema é: Qual bilbioteca escolher?

A biblioteca que escolhi foi a Textual, uma biblioteca usada para apps com interface gráfica, mas que rodam no terminal. Mas, no decorrer do desenvolvimento percebi que ela não é apropriada para esse projeto. Algumas bibliotecas que podem ser melhores para esse caso são:

**Tkinter** \
https://www.geeksforgeeks.org/python/python-gui-tkinter/

**Pygame** \
https://www.pygame.org/wiki/about

Caso precise de ajuda escolhendo uma paleta de cores: \
https://lospec.com/palette-list

Caso precise converter texto em ASCII ART: \
https://patorjk.com/software/taag/#p=display&f=Graffiti&t=Type+Something+&x=none&v=4&h=4&w=80&we=false
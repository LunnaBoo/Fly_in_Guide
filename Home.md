# Sobre o desenvolvimento
A parte mais demorada do projeto é o desenvolvimento do front-end, a interface gráfica. Dependendo da biblioteca escolhida, a visualização pode se tornar bastante sofrida. Dito isso, aconselho que se divida o projeto em 5 partes:
1. [[Zone Hubs e Connections]]\
1.5. [[MapParser]]
2. [[Graph]]
3. [[Drones]]
4. [[Simulation]]
5. [[Visualização]]

## Sobre a Visualização como última etapa
Durante o desenvolvimento do meu projeto, comecei a Visualização cedo demais por pensar que me ajudaria a construir o back-end ter uma forma de VER o que está acontecendo na simulação. Mas, considero que isso foi um erro. \
Por causa dessa decisão, perdi semanas de desenvolvimento presa alternando entre front-end e back-end sem conseguir terminar nada em nenhum dos dois. \
O desenvolvimento da interface gráfica é complicado e leva tempo, devido ao fato de que você tem que aprender uma biblioteca nova do zero. Por isso, aconselho que deixe o front-end para o final, quando o back-end estiver no mínimo funcional. \
É perfeitamente possível de se guiar apenas pelas strings de output que representam cada turno da simulação. É inclusive com isso em mente que digo na paǵina [[Drones]] para que o output da simulação seja escrito num arquivo .txt. Isso auxilia bastante na hora de debugar o back-end sem consultar a interface gráfica.
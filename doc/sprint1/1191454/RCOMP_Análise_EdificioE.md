﻿﻿# Edifício E

# Piso 0

O cabo de fibra ótica provém do exterior do edifício ("Passage way to the external ditch"). É colocado na sala E0.4 um IC (Intermediate cross-connect) ao qual é ligado um HC no salão (Horizontal cross-connect). Para cobrir as salas E0.1, E0.2, E0.3, E0.4, E0.5 é colocado um CP (Consolidation Point) na sala E0.3 para distribuir rede entre os outlets das salas. A distribuição de rede para o salão é feita através de um conjunto de CP's devido á grande quantidade de outlets a conectar. É também enviado cabo para o andar superior através do "Celling cable passageway".Por fim para cobrir toda a área é colocado um AP (Router) na sala E0.5.


- 1 Intermediate cross-connect (IC)
- 1 Horizontal cross-connect (HC)
- 8 Consolidation Point (CP) com 48 portas
- 1 Router
- 375 Outlets
- 103 metros de Cabo de Fibra Ótica (Valor aproximado)
- 494 metros de Cabo de Cobre (Valor aproximado)

![Piso 0](E_Floor0.png)

# Piso 1

O cabo proveniente do andar inferior conecta-se a um novo HC (*Horizontal cross-connect*) o qual conecta a dois cp's, um colocado em E1.3 e outro em E1.5 para distribuir rede entre os outlets das salas.

- 1 Horizontal cross-connect (HC)
- 2 Consolidation Point (CP) com 48 portas
- 65 Outlets
- 47 metros de Cabo de Fibra Ótica (Valor aproximado)
- 166 metros de Cabo de Cobre (Valor aproximado)


![Piso 1](E_Floor1.png)


# Medidas

| Medidas |          A(m²)           | Outlets |
| :-----: | :----------------------: | :------ |
|  E0.1   |            46            | 10      |
|  E0.2   |            49            | 10      |
|  E0.3   |            49            | 10      |
|  E0.4   |            58            | 12      |
|  E0.5   |            46            | 10      |
|  Salão  | 	       1613          | 323     |
|  E1.1   |            46            | 10      |
|  E1.2   |            49            | 10      |
|  E1.3   |            76            | 16      |
|  E1.4   |            58            | 12      |
|  E1.5   |            46            | 10      |
|  E1.6   |            32            | 7       |



```
Escala : 2cm <-> 10m
```

```
Real = [(imagem)*10]/2
```

```
Sabendo que que temos que ter 2 outlets por metro quadrado é só fazer a formula resolvente:

10m² ------------- 2 outlets
Área ------------- x outlets

Logo temos que: 

Nº de Outlets por Sala = (A*2)/10
```

```
Piso 0

- Calha 1 -> 33 outlets
- Calha 2 -> 33 outlets
- Calha 3 -> 33 outlets
- Calha 4 -> 32 outlets
- Calha 5 -> 32 outlets
- Calha 6 -> 32 outlets
- Calha 7 -> 32 outlets
- Calha 8 -> 32 outlets
- Calha 9 -> 32 outlets
- Calha 10 -> 32 outlets

|         | Calha 1 | Calha 2 | Calha 3 | Calha 4 | Calha 5 | Calha 6 | Calha 7 | Calha 8 | Calha 9 | Calha 10 |
| :-----: | :-----: | :-----: | :-----: | :-----: | :-----: | :-----: | :-----: | :-----: | :-----: | :------: |
|  CP 1   |    0    |    20   |    33   |    33   |    32   |    32   |    32   |    32   |    32   |    32    |
|  CP 2   |    -    |    0    |    6    |    33   |    32   |    32   |    32   |    32   |    32   |    32    |
|  CP 3   |    -    |    -    |    0    |    0    |    25   |    32   |    32   |    32   |    32   |    32    |
|  CP 4   |    -    |    -    |    -    |    -    |    0    |    10   |    32   |    32   |    32   |    32    |
|  CP 5   |    -    |    -    |    -    |    -    |    -    |    0    |    0    |    28   |    32   |    32    |
|  CP 6   |    -    |    -    |    -    |    -    |    -    |    -    |    -    |    -    |    13   |    32    |
|  CP 7   |    -    |    -    |    -    |    -    |    -    |    -    |    -    |    -    |    0    |    0     |

- CP 1 -> liga a 33 outlets da calha 1 e 15 da calha 2
- CP 2 -> liga a 18 outlets da calha 2 e 30 da calha 3
- ...
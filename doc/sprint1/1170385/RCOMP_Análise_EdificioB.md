# Edifício B

Para este projeto, fiquei encarregue de cobrir o Edifício B o qual era necessário cobrir com outlets em todas todas as salas exceto as salas comuns e também garantir cobertura de Wi-fi. 

# Piso 0

O cabo de fibra ótica que provém do exterior do edifício entra através do *"Passage way to the external ditch"* e atravessa o *"Underfloor cable raceway"* e conseguimos aceder ao cabo através dos *"Floor cable passageway"* nas salas B0.2, B0.3 e B0.4. É colocado na sala B0.2 um IC (*Intermediate cross-connect*) ao qual é ligado um HC (*Horizontal cross-connect*) que por sua vez liga aos *outlets* a sala B0.2. Para cobrir as salas B0.3 e B0.4 é colocado um segundo HC (*Horizontal cross-connect*) na sala B0.3 o qual distribuí rede para as *outlets* das salas B0.3 e B0.4. É também enviado cabo para o andar superior através do *"Celling cable passageway"*.Por fim para cobrir toda a área do Piso são colocados 2 AP's (Routers), um na sala B0.2 e outro na sala B0.3.

Este piso contém:

- 1 Intermediate cross-connect (IC)
- 2 Horizontal cross-connect (HC)
- 11 Consolidation Point (CP)
- 2 Access Point (Ac) ou Routers
- 74 Outlets
- 76 Patch Cords
- 133.3 metros de Cabo de Fibra Ótica (Valor aproximado)
- 583.3 metros de Cabo de Cobre (Valor aproximado)

![Piso 0](B_Floor0.png)




# Piso 1

Para o primeiro Piso simplesmente conecta-se o cabo proveniente do andar inferior a um novo HC (*Horizontal cross-connect*), na sala B1.3, o qual conecta os outlets das salas B1.1, B1.2, B1.3, B1.4 e B1.5. Para as seguintes salas, tal como  no andar inferior, é colocado um HC (*Horizontal cross-connect*) na sala B1.7 o qual distribuí rede para as *outlets* das salas B1.6, B1.7, B1.8 e B1.9. É também colocado um CP (*Consolidation Point*) na sala B1.11 para extender outlets para as salas B1.11 e B1.12. Para cobrir o piso com Wi-Fi são colocados dois AP, um na sala B1.3 e outro na sala B1.7 para permitir um bom sinal de Wi-Fi em todo o piso.

Este piso contém:

- 2 Horizontal cross-connect (HC)
- 1 Consolidation Point (CP) ou Switches
  - 1 Switch com 24 portas
- 2 Access Point (Ac) ou Routers
- 82 Outlets
- 84 Patch Cords
- 68.3 metros de Cabo de Fibra Ótica
- 756.8 metros de Cabo de Cobre

![Piso 1](B_Floor1.png)



# Medidas

As medidas de cada sala de ambos os pisos são:

| Medidas | Ci(cm) | Li(cm) | Cr(m) | Lr(m) |          A(m²)           | Outlets |
| :-----: | :----: | :----: | :---: | :---: | :----------------------: | :------ |
|  B0.2   |  3.7   |  2.0   | 12.76 | 6.09  |          88.04           | 18      |
|  B0.3   |  4.0   |  2.6   | 13.79 | 8.97  |          123.7           | 25      |
|  B0.4   |  2.4   |  5.4   | 8.28  | 18.62 |          154.17          | 31      |
|  B1.1   |  1.1   |  1.5   | 3.79  | 5.17  |          19.59           | 9       |
|  B1.2   |  1.4   |  2.4   | 4.83  | 3.48  |            17            | 4       |
|  B1.3   |  1.4   |  2.4   | 4.83  | 3.48  |            17            | 4       |
|  B1.4   |  1.4   |  2.4   | 4.83  | 3.48  |            17            | 4       |
|  B1.5   |  1.4   |  2.4   | 4.83  | 3.48  |            17            | 4       |
|  B1.6   |  1.4   |  2.6   | 4.83  |   9   |          43.47           | 9       |
|  B1.7   |  1.4   |  2.6   | 4.83  |   9   |          43.47           | 9       |
|  B1.8   |  1.4   |  2.6   | 4.83  |   9   |          43.47           | 9       |
|  B1.9   |  1.4   |  3.4   | 4.83  | 13.1  |          63.27           | 13      |
|  B1.10  |  1.4   |  3.1   | 4.83  | 10.69 |          51.63           | 11      |
|  B1.11  |  1.4   |  3.1   | 4.83  | 10.69 |          51.63           | 11      |



## Observações:

```
Escala : 2.9cm <-> 10m
```

```
Real = [(imagem)*10]/2.9
```

```
Sabendo que que temos que ter 2 outlets por metro quadrado é só fazer a formula resolvente:

10m² ------------- 2 outlets
Área ------------- x outlets

Logo temos que: 

Nº de Outlets por Sala = (A*2)/10


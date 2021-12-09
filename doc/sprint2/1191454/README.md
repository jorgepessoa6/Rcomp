RCOMP 2019-2020 Project - Sprint 2 - Member 1191454 folder
===========================================
**Inventário**:

Para o Edifício E as Vlans foram definidas no switch Intermediate Cross-Connect visto que este é um switch um modo Servidor e os restantes switches encontram-se em modo Cliente. A partir daí todas as Vlans nos switches em modo Cliente proveem do switch Servidor quando definidas.

O router depois faz a distribuição de todas as redes necessárias para as respetivas Vlans logo este encontra-se ligado ao Intermediate Cross-Connect.

No Piso 0, para além do IC, HC (Horizontal Cross-Connect), CP (Consolidation Points) e AP (Acess Points) definidos no Trabalho do Sprint 1, existe também 1 PC, 1 Laptop, 1 Router e 1 Telefone.

No Piso 1, relativamente ao trabalho do Sprint 1, foi acrescentado 1 PC e 1 Server.



**Decisões tomadas:**

Foi utilizada uma Topologia que aparenta um triângulo de forma a que a spanning tree funcione, ou seja, de forma a que no caso de uma ligação falhar, haver sempre mais uma alternativa de as mensagens chegarem ao seu destino, excepto nos casos onde há apenas uma ligação a fazer em que a solução foi criar uma ligação dupla como acontece entre o IC do piso 0 para o HC do piso 0 e do piso 1, e também entre o HC do piso 0 e o CP8.



**Endereçamento da Rede:**

No Edifício E o endereçamento da rede está definido no intervalo 10.166.232.1 a 10.166.233.252 segundo a tabela seguinte:

|                End Devices                |       IP       |    Gateway     |   Subnet Mask   | Prefixo da Rede |        Vlan         |
| :---------------------------------------: | :------------: | :------------: | :-------------: | :-------------: | :-----------------: |
|        End User Piso 0 (40 nodes)         |  10.166.232.1  | 10.166.232.42  | 255.255.255.192 |       /26       | 350 (E_ground_floor)|
|        End User Piso 1 (45 nodes)         | 10.166.232.84  | 10.166.232.129 | 255.255.255.192 |       /26       | 351 (E_floor_one)   |
| Wireless Laptop (WiFi Network) (60 nodes) | 10.166.232.190 | 10.166.232.250 | 255.255.255.192 |       /26       | 352 (E_wifi)        |
|         Server (DMZ) (250 nodes)          |  10.166.233.1  | 10.166.233.252 |  255.255.255.0  |       /24       | 353 (E_DMZ)         |

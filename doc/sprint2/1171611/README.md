RCOMP 2019-2020 Project - Sprint 2 - Member 1171611 folder
===========================================
**Inventário**:

Para o Edifício D as Vlans foram definidas no switch Intermediate Cross-Connect visto que este é um switch um modo Servidor e os restantes switches encontram-se em modo Cliente. A partir daí todas as Vlans nos switches em modo Cliente proveem do switch Servidor quando definidas.

O router depois faz a distribuição de todas as redes necessárias para as respetivas Vlans logo este encontra-se ligado ao Intermediate Cross-Connect.

No Piso 0, para além do IC, HCs (Horizontal Cross-Connect) e CPs (Consolidation Points) APs (Acess Points) definidos no Trabalho do Sprint 1, existe também 1 PC, 1 Laptop, 1 Servidor, 1 Router e 1 Telefone.

No Piso 1, relativamente ao trabalho do Sprint 1, foi acrescentado 1 PC.



**Decisões tomadas:**

Foi utilizada uma Topologia que aparenta um triângulo de forma a que a spanning tree funcione, ou seja, de forma a que no caso de uma ligação falhar, haver sempre mais uma alternativa de as mensagens chegarem ao seu destino.

No caso do Piso 1, visto que só existe uma ligação para o Piso inferior (IC do Piso 0 para o HC do Piso 1) não foi aplicada a Topologia acima mencionada nessa ligação. Foi antes feita uma dupla ligação. 



**Endereçamento da Rede:**

No Edifício D o endereçamento da rede está definido no intervalo 10.166.230.1 a 10.166.231.252 segundo a tabela seguinte:

|                End Devices                |       IP       |    Gateway     |   Subnet Mask   | Prefixo da Rede |        Vlan         |
| :---------------------------------------: | :------------: | :------------: | :-------------: | :-------------: | :-----------------: |
|        End User Piso 1 (50 nodes)         |  10.166.230.1  | 10.166.230.52  | 255.255.255.192 |       /26       | 346 (D_Floor1_VLAN) |
|        End User Piso 0 (40 nodes)         | 10.166.230.79  | 10.166.230.120 | 255.255.255.192 |       /26       | 345 (D_Floor0_VLAN) |
| Wireless Laptop (WiFi Network) (60 nodes) | 10.166.230.193 | 10.166.230.254 | 255.255.255.192 |       /26       |  347 (D_Wifi_VLAN)  |
|         Server (DMZ) (250 nodes)          |  10.166.231.1  | 10.166.231.252 |  255.255.255.0  |       /24       |  348 (D_DMZ_VLAN)   |


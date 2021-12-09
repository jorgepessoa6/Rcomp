RCOMP 2019-2020 Project - Sprint 2 - Member 1180761 folder
===========================================
**Inventário**:

Para o Edifício C as Vlans foram definidas no switch Intermediate Cross-Connect visto que este é um switch um modo Servidor e os restantes switches encontram-se em modo Cliente. A partir daí todas as Vlans nos switches em modo Cliente proveem do switch Servidor quando definidas.

O router depois faz a distribuição de todas as redes necessárias para as respetivas Vlans logo este encontra-se ligado ao Intermediate Cross-Connect.

No Piso 0, para além do IC, HCs (Horizontal Cross-Connect), CPs (Consolidation Points) e APs (Acess Points) definidos no Trabalho do Sprint 1, existe também 1 PC, 1 Laptop, 1 Servidor, 1 Router e 1 Telefone.

No Piso 1, relativamente ao trabalho do Sprint 1, foi acrescentado 1 PC.



**Decisões tomadas:**

Foi utilizada uma Topologia que aparenta um triângulo de forma a que a spanning tree funcione, ou seja, de forma a que no caso de uma ligação falhar, haver sempre mais uma alternativa de as mensagens chegarem ao seu destino.

No caso do Piso 1, visto que só existe uma ligação para o Piso inferior (IC do Piso 0 para o HC do Piso 1) não foi aplicada a Topologia acima mencionada nessa ligação. 



**Endereçamento da Rede:**

No Edifício D o endereçamento da rede está definido no intervalo 10.166.230.1 a 10.166.231.252 segundo a tabela seguinte:

|                End Devices                |       IP       |    Gateway     |   Subnet Mask   | Prefixo da Rede |        Vlan         |
| :---------------------------------------: | :------------: | :------------: | :-------------: | :-------------: | :-----------------: |
|        End User Piso 1 (44 nodes)         |  10.166.228.1  | 10.166.228.45  | 255.255.255.192 |       /26       | 341 (C_Floor1_VLAN) |
|        End User Piso 0 (40 nodes)         | 10.166.228.84  | 10.166.228.125 | 255.255.255.192 |       /26       | 340 (C_Floor0_VLAN) |
| Wireless Laptop (WiFi Network) (60 nodes) | 10.166.228.169 | 10.166.228.230 | 255.255.255.192 |       /26       |  342 (C_Wifi_VLAN)  |
|         Server (DMZ) (250 nodes)          |  10.166.229.1  | 10.166.229.251 |  255.255.255.0  |       /24       |  343 (C_DMZ_VLAN)   |

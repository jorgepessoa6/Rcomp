RCOMP 2019-2020 Project - Sprint 2 - Member 1170385 folder
===========================================
**Inventário**:

Para o Edifício B as Vlans foram definidas no switch Intermediate Cross-Connect visto que este é um switch um modo Servidor e os restantes switches encontram-se em modo Cliente. A partir daí todas as Vlans nos switches em modo Cliente proveem do switch Servidor quando definidas.

O router depois faz a distribuição de todas as redes necessárias para as respetivas Vlans logo este encontra-se ligado ao Intermediate Cross-Connect.

No Piso 0, para além do IC, HCs (Horizontal Cross-Connect) e CPs (Consolidation Points) APs (Acess Points) definidos no Trabalho do Sprint 1, existe também 1 PC, 1 Laptop, 1 Servidor, 1 Router e 1 Telefone.

No Piso 1, relativamente ao trabalho do Sprint 1, foi acrescentado 1 PC. 
Apenas foram incluídos os End Devices requesitados no enunciado do sprint2.



**Decisões tomadas:**

Foi utilizada uma Topologia que baseia-se em duplicação de alguns cabos de forma a que a spanning tree funcione, ou seja, de forma a que no caso de uma ligação falhar, haver sempre mais uma alternativa de as mensagens chegarem ao seu destino garantindo assim funcionamento de STP.




**Endereçamento da Rede:**

No Edifício B o endereçamento da rede está definido no intervalo 10.166.226.1 a 10.166.227.255 segundo a tabela seguinte:

|                End Devices                |       IP       |    Gateway     |   Subnet Mask   | Prefixo da Rede |        Vlan         |
| :---------------------------------------: | :------------: | :------------: | :-------------: | :-------------: | :-----------------: |
|        End User Piso 0 (60 nodes)         |  10.166.226.1  | 10.166.226.72  | 255.255.255.128 |       /25       | 335 (B_Floor1_VLAN) |
|        End User Piso 1 (70 nodes)         | 10.166.226.150 | 10.166.226.210 | 255.255.255.128 |       /25       | 336 (B_Floor0_VLAN) |
| Wireless Laptop (WiFi Network) (100 nodes)|  10.166.227.1  | 10.166.227.102 | 255.255.255.128 |       /25       |  337 (B_Wifi_VLAN)  |
|         Server (DMZ) (12 nodes)           | 10.166.227.241 | 10.166.227.254 | 255.255.255.240 |       /28       |  338 (B_DMZ_VLAN)   |


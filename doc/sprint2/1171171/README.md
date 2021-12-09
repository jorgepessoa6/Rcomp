RCOMP 2019-2020 Project - Sprint 2 - Member 1171171 folder
===========================================

**Inventário**:

Para o Edifício A as Vlans foram definidas no switch Main Cross-Connect visto que este é um switch um modo Servidor e os restantes switches encontram-se em modo Cliente. A partir daí todas as Vlans nos switches em modo Cliente proveem do switch Servidor quando definidas.

O router depois faz a distribuição de todas as redes necessárias para as respetivas Vlans logo este encontra-se ligado ao Intermediate Cross-Connect.

No Piso 0, para além do  HC (Horizontal Cross-Connect) e CPs (Consolidation Points) APs (Acess Points) definidos no Trabalho do Sprint 1, existe também 1 PC, 1 Laptop e 1 Telefone.

No Piso 1, para além do  HC (Horizontal Cross-Connect), do MC(Main Cross-Connect), do IC(Intermediate Cross-Connect), CPs (Consolidation Points) APs (Acess Points) relativamente ao trabalho do Sprint 1, foi acrescentado um PC e um DMZ.



**Decisões tomadas:**

Foram utilizadas ligações duplas entre switches para garantir redundância e assim, caso haja uma quebra de conneção, é assegurada a segurança da network. Tal foi aplicado tanto para o campus/backbone como para o edifício A.



**Endereçamento da Rede:**

No Edifício A são utilizadas as redes: 10.166.224.0 e 10.166.225.0

Os valores foram atribuidos segundo a tabela seguinte:

|                End Devices                |       IP       |    Gateway     |   Subnet Mask   | Prefixo da Rede |        Vlan         |
| :---------------------------------------: | :------------: | :------------: | :-------------: | :-------------: | :-----------------: |
|        End User Piso 1 (40 nodes)         |  10.166.224.1  | 10.166.224.43  | 255.255.255.192 |       /26       | 330 (A_Floor1_VLAN) |
|        End User Piso 0 (40 nodes)         | 10.166.224.84  | 10.166.224.125 | 255.255.255.192 |       /26       | 331 (A_Floor1_VLAN) |
| Wireless Laptop (WiFi Network) (24 nodes) | 10.166.224.226 | 10.166.224.251 | 255.255.255.224 |       /27       |  332 (A_Wifi_VLAN)  |
|          Server (DMZ) (70 nodes)          |  10.166.225.1  | 10.166.225.72  | 255.255.255.128 |       /24       |  334 (A_DMZ_VLAN)   |

-Fake ISP Adress: 190.5.200.89

**Campus:**

Foi reservado o Endereço 10.166.234.0/25 para o Campus. Foram distribuidos os seguintes endereços para cada edificio:

  * 1171171 - Building A- 10.166.234.1/25;

  * 1170385 - Building B- 10.166.234.41/25;

  * 1180761 - Building C- 10.166.234.61/25;

  * 1171611 - Building D- 10.166.234.21/25;

  * 1191454 - Building E- 10.166.234.81/25;


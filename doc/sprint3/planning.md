RCOMP 2019-2020 Project - Sprint 3 planning
===========================================
## Sprint master: 1170385 ##
(This file is to be created/edited by the sprint master only)
# 1. Sprint's backlog #
No sprint 3 a equipa do grupo 4 da turma 2DF compromete-se a realizar as tarefas requisitadas para os edifícios A,B,C,D e E. Sendo estas tarefas as mencionadas a seguir:

| Task  | Task description                                             |
| ----- | ------------------------------------------------------------ |
| T.3.1 | Update the campus.pkt layer three Packet Tracer simulation from the previous sprint, to include the described features in this sprint for building A. |
| T.3.2 | Update the campus.pkt layer three Packet Tracer simulation from the previous sprint, to include the described features in this sprint for building B. Final integration of each member’s Packet Tracer simulation into a single simulation. |
| T.3.3 | Update the campus.pkt layer three Packet Tracer simulation from the previous sprint, to include the described features in this sprint for building C. |
| T.3.4 | Update the campus.pkt layer three Packet Tracer simulation from the previous sprint, to include the described features in this sprint for building D. |
| T.3.5 | Update the campus.pkt layer three Packet Tracer simulation from the previous sprint, to include the described features in this sprint for building E. |

# 2. Technical decisions and coordination #
## 1 - OSPF dymanic routing ##
 - Os static routing serão apagados em todos os routers e as tabelas de routing existentes serão apagadas também, com a exepção do default router do edifício A.
 - A infraestutura passará a ser um domínio OSPF (Sistema Autónomo) e será distribuído em áreas, uma para cada edifício e uma para o backbone.
 - A área respectiva ao backbone contém apenas uma network IPv4 e a vlan respetiva ao backbone. Para cada edifício será atribuída um id correspondente a uma área e cada uma dessas áreas irá conter todas as networks IPv4 contidas no edifício correspondente.

 No momento do Planning foi definido que para Process-ID do OSPF adotar a seguinte nomenclatura:


 - 101 para o Edifício A;
 - 202 para o Edifício B;
 - 303 para o Edifício C;
 - 404 para o Edifício D;
 - 505 para o Edifício E;

 Também para o AREA-NUMBER, seguimos o mesmo estilo:

 - Área 0 para o BackBone;

 - Área 1 para o Edifício A;
 - Área 2 para o Edifício B;
 - Área 3 para o Edifício C;
 - Área 4 para o Edifício D;
 - Área 5 para o Edifício E;

 O membro da equipa encarregue do edíficio A deverá inserir o OSPF routing protocol no default route apontando ao ISP router de onde a informação é originária.

 ## 2 - HTTP servers ##
 Em adição ao servidor já existente, um novo servidor deve ser adicionado á network DMZ local. Assim como o anterior, este terá IPv4 manualmente atribuído. Neste servidor o serviço HTTP deve estar ativo e uma simples página HTML deverá ser criada com o intuito de identificar o edifício em que este se encontra.

 ## 3 - DHCPv4 Service ##
 O router de cada edifício deve providenciar DHCPv4 a todas as networks locais (em cada edifício), excepto para as networks DMZ  e o backbone onde os endereços IPv4 são estáticos e manualmente atribuídos.
 Para a VoIP VLAN, a configuração do DHCP terá que incluir option 150. Esta configuração representa o endereço de IP do endereço TFTP (Trivial File Transfer Protocol) server, que irá ser usado pelos telefones 7960 para fazer download do seu ficheiro de configuração.

## 4 - VoIP service ##
O router de cada edifício providencia serviço de VoIP (Cisco Telephony) para a network local do VoIP (desse edifício). Isto incluí chamadas para outros edifícios como routers com serviço de VoIP.

Na simulação local de VoIP, em cada edifício devem existir no mínimo 2 telefones de IP conectados (modelo 7960 existente no Packet Tracer).
As portas dos switches usadas para conectar aos telefones terão de ter o Voice VLAN ativado e o acesso á VLAN desativado (no switchport access vlan).
Em relação ao encaminhamento de chamada VoIP, quando uma chamada é para um prefixo de telefone atribuído a outro edifício,
a chamada deve ser encaminhada para os serviços de telefonia em execução no router do respectivo edifício.

Os números de linha atribuídos para cada edifício foram os seguintes: 1001 e 1002 para o edifício A, 2001 e 2002 para o edifício B, 3001 e 3002 para o edifício C, 4001 e 4002 para o edíficio D e por fim 5001 e 5002 para o edifício E.


## 5 -  DNS ##
Serão establecidos dominios DNS independentes para cada edifício. O membro da equipa responsável pelo edifício A criará um nome de domínio DNS correspondente ao nome do repositório da equipa. No nosso caso o nome atribuído será "rcomp-19-20-2DF-G4". Este será o domínio de nível mais alto portanto será usado como domínio raiz. Os membros da equipa responsáveis por outros edifícios criarão domínios locais com o formato "edifício-X.rcomp-19-20-2DF-G4". 

Em cada edifício, deve haver um servidor DNS para dar suporte ao domínio DNS local, o servidor que
foi adicionado a cada DMZ, no sprint anterior, deve ser usado.

Todos os servidores DNS devem ter o nome de DNA não qualificado ns, portanto, para o edifício A, será ns.rcomp19-20-2DF-G4 e, por exemplo, para o edifício C, será ns.building-c.rcomp-19-20-2DF-G4.

### 5.1 Registros NS (Name Server) e glue record ###

   O funcionamento do DNS exige que todos os domínios conheçam os servidores de nomes de cada um de seus subdomínios e também
    para conhecer os servidores de nomes do backbone. O domínio local exige dois registros DNS:
    
    - O próprio registo NS: o nome de registo é o nome do domínio e os dados do DNS;
    - O registo A para o registo NS: o nome do registo é o nome do servidor DNS e
    os dados do registo são o endereço IPv4.

   O último é geralmente chamado de glue record, é necessário porque o registo NS não fornece um IP e
    ainda é necessário entrar em contato com o servidor. Nesse caso, os servidores DNS estão a usar IPv4
    somente se eles estavissem a usar  IPv6. Também deve haver um glue record AAA.
    
 ### 5.2 Outros registros DNS ###
  Todos os servidores HTTP devem ser nomeados server1 (registo A), podem todos ter o mesmo nome desde que pertençam a diferentes dominios DNS.
  Dentro de cada domínio DNS, deve haver um www (CNAME) mapeado para o servidor do mesmo domínio1.
  Um registo chamado web, também foi mapeado para o servidor1 do domínio.
  Um "CNAME" adicional, com nome DNS e mapeado para o registo ns A do domínio, também deve
  existir.

 ### 5.3 Configuração dos clientes DNS (end nodes) ###
  Todos os nós finais em um edifício devem usar o servidor de nomes DNS local e, se suportado, ter o
  nome de domínio DNS padrão definido como o nome de domínio DNS local.
  Para end nodes com configuração automática de DHCP, essas informações devem ser inseridas no local
  Pools DHCP (comandos dns-server e domain-name).
  Para end nodes com configuração manual estática, ou seja, servidores, essas informações devem ser adicionadas manualmente.

## 6 - NAT(Network Address Translation)  
O NAT pode ter vários usos, e muitas vezes é imposto para ocultar endereços privados (NAT dinâmico). O NAT estático,
por outro lado, pode ser usado para redirecionar o tráfego, e é isso que será aplicado neste sprint.

O administrador de cada router aplicará as configurações necessárias de modo a:

    - Solicitações HTTP e HTTPS recebidas na interface do backbone do router são redirecionadas para o servidor HTTP
      na DMZ local. HTTP e HTTPS usam conexões TCP. Serão assumidas as portas de serviço padrão. Os números usados serão 80 e 443.
    - As solicitações de DNS recebidas na interface do backbone do router são redirecionadas para o servidor DNS no local DMZ. O serviço DNS pode usar UDP ou TCP, mas em ambos os casos o número da porta de serviço padrão é 53. Ambos os casos devem ser cobertos.

## 7 - Static Firewall ( ACLs) ##
!!APENAS DEPOIS DE TODAS AS FUNCIONALIDADES ANTERIORES TEREM SIDO BEM TESTADAS É QUE ESTA FUNCIONALIDADE DEVE SER IMPLEMENTADA!!!

As políticas de acesso ao tráfego (quais pacotes serão permitidos ou não) serão implementadas nos routers, pelo
administrador responsável por cada router. Serão particularmente restritivos ao tráfego trocado com o
DMZ local e tráfego destinado ao próprio router.
    Numa precedência de primeira ordem as politicas de acesso são as seguintes:
    
    - 1st
      - Block all spoofing, as far as possible. Internal spoofing from local networks, the DMZ may be
      excluded. External spoofing in traffic incoming from the backbone network.
    -2nd 
      - All ICMP echo requests and echo replies are always allowed.
    -3rd
      - All traffic to the DMZ is to be blocked, except for the DNS service and HTTP/HTTPS services to
        the corresponding servers. All traffic incoming from the DMZ is allowed.
    -4th
      - All traffic directed to the router itself (with a destination IPv4 node address belonging to the router)
       is to be blocked, except for the traffic required for the current features to work.
    -5th
      - Remaining traffic passing through the router should be allowed.

Em relação ao quarto ponto, irá ser incluido uma série de serviços que terão de ser permitidos nas networks que estes são requisitados. Alguns a não esquecer são:

- O serviço DHCPv4;
- O serviço TFTP;
- O serviço ITS;
- O Tráfego OSPF;
- E o tráfego relacionado com as recentemente reforçadas regras estáticas do NAT.



# 3. Subtasks assignment #
-1170385 (Rui Mendes) Juntar os edificios no campus, planning e review.Configurar OSPF, servidores HTTP, serviço DHCPv4, serviço VoIP, DNS, NAT e Static Firewall para o Edifício B.

-1171611 (Miguel Fortes) Desenvolver o relatório adequeado. Configurar OSPF, servidores HTTP, serviço DHCPv4, serviço VoIP, DNS, NAT e Static Firewall para o Edifício C.

-1171171 (Pedro Cardoso) Configurar OSPF, servidores HTTP, serviço DHCPv4, serviço VoIP, DNS, NAT e Static Firewall para o Edifício A.

-1180761 (Jorge Pessoa) Configurar OSPF, servidores HTTP, serviço DHCPv4, serviço VoIP, DNS, NAT e Static Firewall para o Edifício D.

-1191454 (Bruno Pereira) Configurar OSPF, servidores HTTP, serviço DHCPv4, serviço VoIP, DNS, NAT e Static Firewall para o Edifício E.


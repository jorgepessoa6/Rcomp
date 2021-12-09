RCOMP 2019-2020 Project - Sprint 2 planning
===========================================
### Sprint master: 1171611 ###
(This file is to be created/edited by the sprint master only)
# 1. Sprint's backlog #
- Development of a layer two and layer three Packet Tracer simulation for building A, and also encompassing the campus backbone. Integration of every members’ Packet Tracer simulations into a single simulation.
- Development of a layer two and layer three Packet Tracer simulation for building B, and also encompassing the campus backbone.
- Development of a layer two and layer three Packet Tracer simulation for building C, and also encompassing the campus backbone.
- Development of a layer two and layer three Packet Tracer simulation for building D, and also encompassing the campus backbone.
- Development of a layer two and layer three Packet Tracer simulation for building E, and also encompassing the campus backbone.

# 2. Technical decisions and coordination #
We decided that we should, for each building, place both floor blueprints in the same image to use in the Packet Tracer file instead of using clusters.

We used the default blueprints instead of the ones we achieved in sprint 1.

# 3. Subtasks assignment #
The third octet of each network was distributed as follows, with the given address starting at 10.166.224.0:

  * 1171171 - Building A. [10.166.224.0 - 10.166.225.255]   Backbone [10.166.234.0 - 10.166.234.128];

  * 1170385 - Building B. [10.166.226.0 - 10.166.227.255];

  * 1180761 - Building C. [10.166.228.0 - 10.166.229.255];

  * 1171611 - Building D. [10.166.230.0 - 10.166.231.255];

  * 1191454 - Building E. [10.166.232.0 - 10.166.233.255];

    

The Vlans were distributed in the following manner:

  * 1171171 - Building A. Vlan[330-334], Campus Vlan[355];

  * 1170385 - Building B. Vlan[335-339];

  * 1180761 - Building C. Vlan[340-344];

  * 1171611 - Building D. Vlan[345-349];

  * 1191454 - Building E. Vlan[350-354];

    


# Moore type cellular automata gossip and ising consensus condition simulation introduction

This simulation demonstrates the spread of a gossip and Ising consensus with the cellular automaton model. It consists of a number of identical cells representing peers in the network arranged in a regular grid. Each cell can be in one of two states - for example "on" or "off", or "heard" or "not heard". The states indicate settings or actions of cells. Timeindex goes through the simulation in steps. At each time step, the state of each cell may change. The state of a cell after any time step is determined by a series of rules that indicate how that state depends on the previous state of that cell and the states of the immediate neighbors of the cell. The same rules are used to update the state of each cell in the grid. The cellular automata model is therefore homogeneous in terms of rules.

## Rules for cellular automata gossip and ising consensus

Cellular automata model local interactions well. Therefore, the simulation is divided into two phases:

- Cellular automata gossip to a predefined percentage. A gossip (transaction) spreads by peers only talk to their immediate neighbors. This kind interaction is local and could be modeled with a cellular automata. Here peers are modeled as cells/patches in netlogo.Each cell has two states: ignorance about the item of gossip or knowing the gossip. And we define colour black indicating a cell that does not know the gossip and color white one that does. Local interaction between peer and neighbors is modelled using the rules of cellular automata as: If the cell is black, and it has one or more white neighbours, consider each white neighbour in turn. For each white neighbour, change to white with some specific probability, otherwise remain black. If the cell is white already, the cell remains white. A gloal gossip percentage variable is defined so that the gossip process can stop at a give percentage to proceed with next step: Ising model consensus.Cellular automata gossip stops at a predefined percentage. A gossip (transaction) spreads from peers only with their immediate neighbors. This type of interaction is local and could be modeled using a cellular automaton. Here, peers are modeled as cells / patches in Netlogo. Each cell has two states: ignorance of gossip or knowing gossip. And we define color black, which indicates a cell that does not know the gossip and color white knows what that does. The local interaction between peer and neighbor is modeled using the rules of cellular automata: if the cell is black and has one or more white neighbors, look at each white neighbor in turn. For every white neighbor, the cell likely to switch to white, or the cell will stay black. If the cell is already white, the cell stays white. A global gossip percentage variable is defined so that the gossip process can stop at a given percentage to proceed to the next step: Ising model consensus.

- Celluar automata based ising model consensus was first proposed by NKN in whitepaper with solid mathematical proofs. Here, in ising model consensus simulation, we define a cell changes state (black or white) according to the joint states of all of its neighbours.Peers might adopt a vote only if the majority of their neighbors have already adopted it. Also, we define that a cell has a Moore type neighborhood, which indicates that each cell has eight neighbors around. Base on these conditions, the rule of cellular automata can be set as: the new state of a cell is the state of the majority of the cell��s Moore neighbours, or the cell��s previous state if the neighbours are equally divided between black and white, indicating ignorance of gossip or knowing gossip. Since there are eight Moore neighbors. To reach ising consensus, we define a threshold of sum of neighbor vote count as K/2, where K denotes the total number of neighbors. Thus, the rule says that a cell is black if there are four or more black cells surrounding it, white if there are four or more white cells around
it, or remains in its previous state if there are four black and four white neighbors.BTW, the initial state of this consensus is defined by the phase 1 where a partial gossip process at a given gossip percentage.


## Simulation Results Analysis

- For the process of cellular automata gossip, it is interesting to observe the effect of the different probabilities of communication of gossip by making a corresponding modification of the rules. The simulation shows that the spread of gossip by local, peer-to-peer Interactions are not seriously hampered by a low probability of transmission at any given time, although low probabilities result in slow propagation.

- For ising model consensus, setting a threshold value of K/2 can gurantee the consensus can be reached globally. However, it is esstential to define proper voting rule and randomize gossip distribution to enhance fault tolerance and covergence time.


Cellular automata with 4 neighbors vote 1 then it votes 1 when gossip reach 75% and randomized, as below
![Cellular automata with 4 neighbors vote 1 then it votes 1 when gossip reach 75% and randomized](https://github.com/NKNetwork/nkn/blob/master/simulation/cellular_automata_gossip_ising_sim/Moore_CA_neighbors_set_vote_1-vote_when_halfKis4_gossip_75percent_on%20the_entire_network_randomized.png)

Cellular automata with 4 neighbors vote 1 then it keeps its original state when gossip reach 75% and randomized, as below
![Cellular automata with 4 neighbors vote 1 then it keeps its original state when gossip reach 75% and randomized](https://github.com/NKNetwork/nkn/blob/master/simulation/cellular_automata_gossip_ising_sim/Moore_CA_neighbors_set_vote_1_when_halfKis4_gossip_75percent_on%20the_entire_network_randomized.png)

Cellular automata with 4 neighbors vote 1 then it votes 1 when gossip reach 75% and randomized dynamically, as below
![Cellular automata with 4 neighbors vote 1 then it votes 1 when gossip reach 75% and randomized dynamically](https://github.com/NKNetwork/nkn/blob/master/simulation/cellular_automata_gossip_ising_sim/Moore_CA_neighbors_set_vote_1_when_halfKis4_gossip_75percent_on%20the_entire_network_dynamic_randomized.png)


## License

Apache License 2.0
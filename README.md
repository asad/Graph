# Graph Analysis: Load Points and Choke Points

## Overview

This project implements algorithms for identifying **load points** and **choke points** in directed weighted graphs. These concepts are inspired by metabolic pathway analysis but are applicable to various domains, including traffic networks, supply chains, and healthcare provider networks.

### Key Features:
- **Load Points**: Nodes acting as traffic hotspots, computed using k-shortest paths and nearest neighbors.
- **Choke Points**: Critical nodes or edges whose removal disrupts network connectivity or significantly increases path lengths.
- **Centrality Analysis**: Includes degree, betweenness, and closeness centrality for understanding node importance.

### Applications:
- **Metabolic Pathways**: Identifying critical enzymes or metabolites for drug targeting.
- **Traffic Networks**: Highlighting congested intersections or vulnerable roads.
- **Supply Chains**: Detecting overloaded warehouses or critical delivery routes.
- **Healthcare Networks**: Pinpointing critical hospitals or referral hubs.

---

## Algorithms

1. **k-Shortest Paths**: Identifies multiple paths between nodes for redundancy and analysis.
2. **Load Algorithm**: 
   - Inbound and outbound load contributions calculated as:
     $$
     L_{m(\text{in/out})} = \ln \left[ \frac{\frac{p_{m(\text{in/out})}}{k_{m(\text{in/out})}} + \epsilon}{\frac{\sum_{i=1}^M P_{i(\text{in/out})}}{\sum_{i=1}^M K_{i(\text{in/out})}} + \epsilon} \right]
     $$
   - Where:
     - \( p_{m(\text{in/out})} \): Number of k-shortest paths through a node.
     - \( k_{m(\text{in/out})} \): Nearest neighbors for the node.
     - \( P_{i(\text{in/out})} \), \( K_{i(\text{in/out})} \): Global path and neighbor sums.
     - \( \epsilon \): Small constant to avoid division by zero.

3. **Choke Points**:
   - **Edge-Based**:
     $$
     \text{Cost}(e) = \frac{\text{New Path Length} + \epsilon}{\text{Original Path Length} + \epsilon}
     $$
   - **Node-Based**: Nodes with degree 2 whose removal isolates or significantly disrupts connectivity.

4. **Centrality Measures**:
   - Degree, Betweenness, and Closeness centrality to rank node importance.

---

## Example

### Input Graph (Traffic Network):
Nodes represent cities, and edges represent roads with weights as travel times:
```plaintext
City A --5--> City B --10--> City C
City A --15--> City C --3--> City D --8--> City E
City B --20--> City D
City A --25--> City E

## Outputs:

- **Load Points**: Nodes with high traffic contributions.
- **Choke Points**: Nodes or edges critical for connectivity.
- **Centrality Metrics**: Degree, Betweenness, and Closeness centralities for each node.

---

## Reference

Rahman, S. A., & Schomburg, D. (2006). Observing local and global properties of metabolic pathways: ‘load points’ and ‘choke points’ in the metabolic networks.  
*Bioinformatics*, 22(14), 1767–1774.  
[DOI: 10.1093/bioinformatics/btl181](https://doi.org/10.1093/bioinformatics/btl181)  
[Access Full Article](https://academic.oup.com/bioinformatics/article/22/14/1767/227488)



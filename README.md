# Graph Analysis: Load Points and Choke Points

---

## Algorithms

1. **k-Shortest Paths**  
   Identifies multiple paths between nodes for redundancy and analysis.

2. **Load Algorithm**  
   Inbound and outbound load contributions calculated as:  
   **L_in/out = ln [(p_in/out / k_in/out) / (Σ P_in/out / Σ K_in/out)]**  

   Where:
   - **p_in/out**: Number of k-shortest paths through a node.
   - **k_in/out**: Nearest neighbors for the node.
   - **Σ P_in/out**: Global path sums across all nodes.
   - **Σ K_in/out**: Global neighbor sums across all nodes.
   - **epsilon**: A small constant to avoid division by zero.

3. **Choke Points**  
   - **Edge-Based**: Cost(e) = (New Path Length + epsilon) / (Original Path Length + epsilon)  
   - **Node-Based**: Nodes with degree 2 whose removal isolates or significantly disrupts connectivity.

4. **Centrality Measures**  
   Degree, Betweenness, and Closeness centralities to rank node importance.

---

## Example

### Input Graph (Traffic Network):
Nodes represent cities, and edges represent roads with weights as travel times:
```plaintext
City A --5--> City B --10--> City C
City A --15--> City C --3--> City D --8--> City E
City B --20--> City D
City A --25--> City E
```
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



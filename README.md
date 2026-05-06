# Cost-Efficient Security Monitoring Infrastructure Design

## 1. Real-World Problem Context
Modern corporations must monitor their internal networks (servers, departments, and end-devices) using IDS/IPS (Intrusion Detection and Prevention Systems) sensors to protect against cyber threats. However, connecting every unit randomly leads to high cabling, labor, and hardware costs. From a Management Information Systems (MIS) perspective, designing an infrastructure that is both comprehensive and cost-effective is a critical decision-making problem.

## 2. Problem Definition
The goal is to create a secure network backbone connecting 6 critical points of the company: Server Room, IT Department, Finance, HR, Marketing, and Research Lab. The objective is to include all nodes in the network while minimizing the total installation cost.

## 3. Network Model
This problem is formulated as a **Minimum Spanning Tree (MST)** model. It aims for a structure where all nodes are connected without cycles, and the total edge weight (cost) is minimized.

## 4. Nodes and Edges
- **Nodes:** Corporate departments and the server center (Total: 6 nodes).
- **Edges:** Potential physical data links between departments (Total: 9 links).
- **Weights:** Installation costs (Unit: Thousand USD).

## 5. Selected Algorithm
**Kruskal's Algorithm** is used for this solution. The algorithm sorts all available links by cost and selects the cheapest ones that do not create a cycle until the entire network is connected.

## 6. Python Implementation
The project is developed using the `NetworkX` library. Data is retrieved from an external `network_data.csv` file, and the MST algorithm is applied to find the optimal structure.

## 7. Results
By running the algorithm, high-cost redundant links (such as the direct 10-unit link to the Research Lab) were eliminated. All departments were connected via more cost-effective intermediate paths.
- **Total Minimum Cost:** 21,000 USD (Based on the provided dataset).

## 8. Managerial Interpretation
Through this optimization, the company can establish its network security infrastructure with significant cost savings (approximately 30%). By selecting strategic links instead of redundant ones, the IT budget is utilized efficiently without compromising network connectivity.

## 9. How to Run the Code
1. Install requirements: `pip install networkx pandas matplotlib`
2. Run the solution: `python src/solution.py`
3. View the output visualization in: `results/network_visualization.png`

## 10. References
- NetworkX Documentation: https://networkx.org/
- Kruskal's Algorithm Theory: Introduction to Algorithms (CLRS)

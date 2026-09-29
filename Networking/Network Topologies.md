## What is a Topology?
Topology describes how devices (computers, routers, etc.) are **connected and communicate** with each other.

---
## A. Bus Topology
- **Structure**: All devices share a single communication line (backbone).
- **Advantages**: Easy to implement, cost-effective.
- **Disadvantages**: 
- Failure of the main cable stops the network.
- Performance degrades as more devices are added.
- **Use case**: Small networks, temporary setups.

<img width="1024" height="559" alt="image" src="https://github.com/user-attachments/assets/7a13c1b9-177e-491f-b1e5-0d7f7ac6645a" />

---
## B. Star Topology
- **Structure**: All devices connect to a central hub or switch.
- **Advantages**:
- Easy to manage and troubleshoot.
- Failure of one device does not affect others.
- **Disadvantages**:
- Central hub failure stops the network.
- Requires more cable than bus topology.
- **Use case**: Modern LANs (most common topology).

<img width="1024" height="559" alt="image" src="https://github.com/user-attachments/assets/49d469ca-d8f6-45e1-9c1d-960cf513826b" />


---
## C. Ring Topology
- **Structure**: Each device connects to two neighbors forming a closed loop.
- **Advantages**:
- Data flows in one direction, reducing packet collisions.
- **Disadvantages**:
- Failure of a single device or link can disrupt the entire network.
- **Use case**: Token Ring networks, fiber optic networks.

<img width="1024" height="559" alt="image" src="https://github.com/user-attachments/assets/0beb881c-0cc1-4706-886b-808f068f758f" />


---
## D. Mesh Topology
- **Structure**: Every device connects to every other device directly.
- **Advantages**:
- High fault tolerance and reliability.
- Data can take multiple paths to reach the destination.
- **Disadvantages**:
- Expensive and complex due to high cabling requirements.
- **Use case**: Critical networks (e.g., military or telecom backbone networks).

<img width="1024" height="559" alt="image" src="https://github.com/user-attachments/assets/b7423a81-c706-4486-b4c5-b84eb88a48e0" />

---
## E. Tree Topology
- **Structure**: Combination of star and bus topologies, hierarchical arrangement.
- **Advantages**:
- Scalable and easy to manage.
- Failure of one branch doesn’t affect others.
- **Disadvantages**:
- Failure of the root affects the whole branch.
- **Use case**: Large organizations with departmental segmentation.

---
## F. Hybrid Topology
- **Structure**: Combination of two or more topologies.
- **Advantages**: Flexible, scalable, and optimized for specific needs.
- **Disadvantages**: Complex to design and maintain.
- **Use case**: Large-scale networks requiring both reliability and efficiency. 

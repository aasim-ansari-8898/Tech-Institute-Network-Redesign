# Body

The project, spanning over two years, aims to replace the existing hubs with access switches. In the initial phase, priority will be given to Building B and Building C, with a distribution switch and firewall being added. The second phase will focus on Building A and Building D and include the deployment of a redundant distribution switch and firewall, along with the implementation of WiFi.

Existing servers will be used to provide essential services like DHCP, DNS, Authentication, WLC, CUPS server, and Zabbix. This phased approach ensures that critical infrastructure upgrades are completed first, followed by enhancements to network redundancy and wireless capabilities.

## A. IP Addressing Scheme
The following table outlines the IP addressing scheme for the campuses:

| CAMPUS ROOMS | LAN IP add   | MASK       | Vlan |
|--------------|--------------|------------|------|
| A 1          | 172.16.10.0  | /26        | 10   |
| A 2          | 172.16.10.64 | /26        | 11   |
| A 3          | 172.16.10.128| /26        | 12   |
| A 4          | 172.16.10.192| /26        | 13   |
| A 5*         | 172.16.11.0  | /26        | 14   |
| A 6*         | 172.16.11.64 | /26        | 15   |
| B 1          | 172.16.11.128| /26        | 16   |
| B 2          | 172.16.11.192| /26        | 17   |
| B 3          | 172.16.12.0  | /26        | 18   |
| B 4          | 172.16.12.64 | /26        | 19   |
| C 1          | 172.16.12.128| /26        | 20   |
| C 2          | 172.16.12.192| /26        | 21   |
| C 3          | 172.16.13.0  | /26        | 22   |
| C 4          | 172.16.13.64 | /26        | 23   |
| C 5          | 172.16.13.128| /26        | 24   |
| C 6          | 172.16.13.192| /26        | 25   |
| C 7          | 172.16.14.0  | /26        | 26   |
| D 1          | 172.16.14.64 | /26        | 27   |
| D 2          | 172.16.14.128| /26        | 28   |
| D 3          | 172.16.14.192| /26        | 29   |
| D 4          | 172.16.15.0  | /26        | 30   |
| D 5          | 172.16.15.64 | /26        | 31   |
| C 14 - Servers| 172.16.86.0 | /25        | 86   |

### WLAN Configuration
The WLAN configuration is as follows:

| WLAN        | Building | Users | LAN IP add       | Mask      |
|-------------|----------|-------|------------------|-----------|
| Students    | A        | 500   | 192.168.128.0    | /22       |
|             | B        | 6500  | 192.168.0.0      | /18       |
|             | C        | 350   | 192.168.136.0    | /23       |
|             | D        | 100   | 192.168.140.0    | /24       |
| Management  | A        | 120   | 192.168.141.0    | /24       |
|             | B        | 120   | 192.168.142.0    | /24       |
| Guest       | A        | 500   | 192.168.132.0    | /22       |
|             | B        | 6500  | 192.168.64.0     | /18       |

## B. Network Diagrams
- **Phase 1 & 2 Diagram**: ![Phase Diagram](../Diagrams/Network_Diagram_Phase.png)

## C. Design Document
### Hardware and Software at Each Stage of Migration

#### Phase 1: Year 1
1. **Access Switches**
   - **Hardware**: EnGenius ECS1552P
   - **Purpose**: Replace outdated 3COM HUBs with advanced switches that can support PoE devices like IP phones and Wi-Fi access points.

2. **Server NIC Cards**
   - **Hardware**: StarTech I225-V
   - **Purpose**: Upgrade server NICs to handle increased data transfer speeds.

3. **Distribution Switch**
   - **Hardware**: Edge-Core AS5835-54X
   - **Purpose**: Serve as a high-capacity distribution point for aggregating traffic from access switches.

4. **Router/Firewall**
   - **Hardware**: Palo Alto Networks PA-1410
   - **Purpose**: Enhance security by protecting the network edge.

5. **SFP Transceivers**
   - **Hardware**: TP-Link TL-SM5110-SR
   - **Purpose**: Enable high-speed fiber connections.

#### Phase 2: Year 2
1. **Additional Access Switches**
   - **Hardware**: EnGenius ECS1552P
   - **Purpose**: Replace outdated components in Campuses A and D.

2. **Redundant Distribution Switch**
   - **Hardware**: Edge-Core AS5835-54X
   - **Purpose**: Provide redundancy in the distribution layer.

3. **Uninterruptible Power Supply (UPS)**
   - **Hardware**: Eaton 5P 1000VA
   - **Purpose**: Protect critical network equipment from power outages.

4. **Wireless Access Points**
   - **Hardware**: EnGenius Fit6 2x2 Lite
   - **Purpose**: Provide Wi-Fi coverage across all campuses.

5. **Router**
   - **Hardware**: Palo Alto Networks PA-1410
   - **Purpose**: Support expanded remote access capabilities.

## D. Cost Summaries
The project will be executed in two phases, each with a defined budget of CAD 38,000.

### Phase 1 Cost Summary
| Component                  | Brand                | Model              | Feature                      | Count | Total Cost (CAD) |
|---------------------------|----------------------|--------------------|------------------------------|-------|-------------------|
| Access Switches           | EnGenius             | ECS1552P           | L2, 4 x SFP+, 48 x POE      | 25    | $17,549.75        |
| Distribution Switch       | Edge-Core            | AS5835-54X         | L3, 48 x SFP+               | 1     | $8,211.99         |
| SFP Transceivers          | TP-Link              | TL-SM5110-SR       | 10GBase-LR SFP+ LC          | 112   | $4,030.88         |
| Server NIC Cards          | StarTech.com         | I225-V             | 2.5/1Gbps                   | 12    | $875.88           |
| Router                    | Palo Alto Networks    | PA-1410            | Firewall throughput: 6.8 Gbps| 1     | $6,171.99         |

**Total Phase 1 Cost**: $37,662.72  
**Budget**: CAD 38,000  
**Savings**: CAD 149.52  

### Phase 2 Cost Summary
| Component                  | Brand                | Model              | Feature                      | Count | Total Cost (CAD) |
|---------------------------|----------------------|--------------------|------------------------------|-------|-------------------|
| Access Switches           | EnGenius             | ECS1552P           | L2, 4 x SFP+, 48 x POE      | 25    | $17,549.75        |
| Distribution Switch       | Edge-Core            | AS5835-54X         | L3, 48 x SFP+               | 1     | $8,211.99         |
| Wireless Access Points     | EnGenius             | Fit6 2x2 Lite      | 802.11ac Wave 2, 2x2 MIMO   | 30    | $9,116.64         |
| Uninterruptible Power Supply (UPS) | Eaton       | 5P 1000VA          | 1000VA, USB, LCD            | 2     | $859.20           |
| Router                    | Palo Alto Networks    | PA-1410            | Firewall throughput: 6.8 Gbps| 1     | $6,171.99         |

**Total Phase 2 Cost**: $41,609.57  
**Budget**: CAD 38,000  
**Savings**: CAD 3,609.57  

### Overall Summary
**Total Project Cost**: $79,272.29  
**Total Budget**: CAD 76,000  
**Total Savings**: CAD 3,272.29  

## E. Project Implementation Plan
The implementation plan will be executed in two phases over two academic years to address the Tech Institute's critical network performance issues stemming from outdated IT infrastructure.

### Phase One: Year 1
**Timeline:** September 2024 - October 2024
**Tasks:**
   - **Planning and Procurement** (Weeks 1-2)
      - Finalize hardware requirements and configurations.
      - Place orders for equipment and confirm delivery dates.
   - **NIC Card Upgrade** (Week 3)
      - Upgrade server NIC cards to StarTech I225-V.
   - **Access Switch Replacement** (Week 4)
      - Replace existing switches in Campuses B and C.
   - **Distribution Switch Installation** (Week 6)
      - Install and configure Edge-Core AS5835-54X distribution switch.
   - **Final Review and Optimization** (Week 7)
      - Conduct a thorough network review and optimization.

### Phase Two: Year 2
**Timeline:** September 2025 - October 2025
**Tasks:**
   - **Planning and Procurement** (Weeks 1-2)
      - Finalize hardware requirements and configurations for additional switches.
   - **Access Switch Installation** (Week 3)
      - Replace current switches in Campuses A and D.
   - **Distribution Switch and UPS Installation** (Week 4)
      - Install redundant distribution switch and UPS systems.
   - **Router and Access Point Installation** (Week 5)
      - Install and configure routers and access points across all campuses.
   - **Final Review and Optimization Phase** (Week 6)
      - Conduct a comprehensive network review and implement necessary updates.

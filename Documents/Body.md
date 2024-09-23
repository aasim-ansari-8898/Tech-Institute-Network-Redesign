# Body

## A. Introduction
This project addresses critical network performance issues, including slow logins, downloads, and response times from network services such as database queries, printing, and internet browsing. To enhance accessibility and functionality, all campuses will be made WiFi-friendly, allowing users to access the network from any location. Additionally, printing will be enabled from any station to any printer across all campuses, with WiFi access appropriately grouped into "management & staff," "students," and "guests."

A plan will be developed for the implementation of Voice over IP (VoIP) phone sets for desktops, including recommendations for suitable vendors. The project includes a budget of CAD 38,000 per academic year for ISP services at Campus C. 

Network infrastructure improvements will encompass the implementation of core, distribution, and access layers, with consideration for a 20% annual growth rate. Fault tolerance measures, an internet firewall, and a robust uninterruptible power supply (UPS) will be put in place to ensure network reliability and security. Additionally, secure remote login connections will be provided for 400 mobile staff members.

The project will estimate the number of WiFi Access Points required for each campus (A, B, C, and D) and submit a logical design schema/diagram for WiFi Access Points and Wireless LAN Controllers for each campus.

## B. Body
The project, spanning over two years, aims to replace the existing hubs with access switches. In the initial phase, priority will be given to Building B and Building C, with a distribution switch and firewall being added. The second phase will focus on Building A and Building D and include the deployment of a redundant distribution switch and firewall, along with the implementation of WiFi.

Existing servers will be used to provide essential services like DHCP, DNS, Authentication, WLC, CUPS server, and Zabbix. This phased approach ensures that critical infrastructure upgrades are completed first, followed by enhancements to network redundancy and wireless capabilities.

### IP Addressing Scheme
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

## C. Network Diagrams
- **Phase 1 Diagram**: ![Phase 1 Diagram](../Diagrams/Network_Diagram_Phase1.png)
- **Phase 2 Diagram**: ![Phase 2 Diagram](../Diagrams/Network_Diagram_Phase2.png)

## D. Design Document
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

## E. Cost Summaries
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

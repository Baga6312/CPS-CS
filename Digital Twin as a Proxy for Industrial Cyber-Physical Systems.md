# Structured Summary of "Digital Twin as a Proxy for Industrial Cyber-Physical Systems"

## **Problem Statement**  
Resource-constrained devices (e.g., battery-driven sensors) in Industrial Cyber-Physical Systems (ICPSs) face critical challenges:  
- **High energy consumption** leading to short device lifespans.  
- **Low service availability** due to duty cycling or device failures.  
- **Insecure remote control** and governance of devices in risky environments.  
- **Limited security capabilities** on resource-constrained devices.  

---

## **Proposed Solution**  
**Digital Twin as a Proxy (DTaaP):**  
A four-layer architectural model to offload tasks from physical devices to Digital Twins (DTs), addressing:  
1. **Energy Efficiency**: Delegating service requests to DTs to reduce device workload.  
2. **High Availability & State Persistence**: Caching device states for continuous service.  
3. **Remote & Contention Control**: Secure atomic control via DTs.  
4. **Security**: Centralizing authentication/authorization at the proxy layer.  

---

## **Methodology**  
### **Architecture**  
1. **Device Layer**: Physical sensors/actuators (e.g., Raspberry Pi + DHT11 sensor).  
2. **Communication Layer**: MQTT/AMQP for synchronization between DTs and physical twins (PTs).  
3. **Proxy Layer**:  
   - **Eclipse Ditto** framework for DT management.  
   - Features: Policy-based security, REST APIs, message translation.  
4. **Application Layer**: Web/mobile apps interacting with DTs via APIs.  

### **Proof of Concept (PoC)**  
- **DT Creation**: JSON policies for access control, device models, and MQTT connections.  
- **Experimental Setup**:  
  - **Sensing**: Temperature/humidity data collection.  
  - **Actuation**: Two-color LED controlled remotely via DT.  

---

## **Key Results**  
- **Energy Efficiency**:  
  - **20x battery life improvement** (from 33 to 666 days) by reducing device interactions.  
- **Availability**:  
  - DT provided persistent sensor data even during device sleep/failure.  
- **Security**:  
  - Centralized policy-based authentication (e.g., admin vs. observer roles).  
- **Remote Control**:  
  - Demonstrated secure LED actuation via DT (e.g., Figure 7).  

---

## **Limitations**  
- **Contention Control**: Eclipse Ditto lacks atomic control for simultaneous actuator commands.  
- **High Availability**: One-to-one DT-PT mapping limits fault tolerance.  
- **Historical Data**: DTs store only the latest state, not historical data for analytics.  

---

## **Future Work**  
- **Redundancy**: Implement one-to-many/many-to-many DT-PT mappings.  
- **Contention Control**: Add mutual exclusion for concurrent actuator access.  
- **Historical Data**: Integrate time-series storage in DTs.  
- **Extended Evaluations**: Qualitative/quantitative assessments across diverse ICPS use cases.  

---

## **Conclusion**  
DTaaP effectively addresses ICPS challenges by offloading tasks to DTs, improving energy efficiency, security, and availability. The PoC validates the model using Eclipse Ditto, though limitations highlight areas for future research.  

---

**ACM Reference Format**  
Abdullah Aziz, Olov Schelén, and Ulf Bodin. 2023. Digital Twin as a Proxy for Industrial Cyber-Physical Systems. In *icWCSN 2023*. ACM, New York, NY, USA. https://doi.org/10.1145/3585967.3585982  

**Keywords**: Digital Twins, CPS, Industry 4.0, DTaaP.  
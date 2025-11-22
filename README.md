# 🌊 AI + Blockchain Powered MRV Platform for Mangrove & Blue Carbon Projects

A full-stack MRV system that digitizes Measurement, Reporting, and Verification (MRV) using drones, machine learning (for NDVI, canopy and biomass estimation), smart contracts on the Polygon blockchain, IPFS for evidence storage, and a combined mobile field application with a web-based verification dashboard, ensuring tamper-proof, auditable, and transparent carbon accounting while preventing fake or duplicated carbon credits.

---

# 👥 User Roles & Platforms

| Role | Platform | Responsibilities |
|------|----------|------------------|
| 🌐 **Community Head / NCCR Head (Verifier / Admin)** | **Web Dashboard** | Approves projects & MRV, audits CIDs, issues carbon credits |
| 📱 **Field Officer / Project Developer / Surveyor** | **Mobile App** | Captures drone data, uploads documents & sensor logs, triggers MRV |
| 🌍 **Public / Carbon Buyers (Optional)** | Web (Read-Only) | Trace MRV, audit carbon evidence |

---

# 🔎 Problem

- Manual, slow and expensive MRV  
- Easily manipulated reports and duplicate carbon credits  
- No verifiable link to raw drone & sensor evidence  
- Lack of transparency for communities & government (NCCR, State agencies)

    <img width="707" height="543" alt="image" src="https://github.com/user-attachments/assets/47112693-d9b5-470b-8a70-936f02073a60" />


---

# 🚀 Solution

- 🤖 **AI-powered MRV** (NDVI, canopy, tree count, biomass, carbon estimation)
- 🔗 **Blockchain-based MRV registry** on Polygon (via Hardhat)
- 📦 **IPFS storage** for drone images, NDVI, maps, logs & reports
- 📱 **Mobile app** for field data collection
- 💻 **Web dashboard** for NCCR/community verification & approval
- 🌡 **Sensor simulation pipeline** (pH, salinity, temperature, humidity)

---

# 🏗 High-Level System Architecture

<img width="565" height="554" alt="system-architecture" src="https://github.com/user-attachments/assets/c21aa6bd-9738-415c-b70f-56d3005de449" />

---

### 📱 React Native Mobile App
- Login & secure identity  
- Draw project boundary polygon on map  
- Upload drone images + registration documents  
- Upload sensor logs (pH, salinity, temp, humidity)  
- Trigger MRV analysis  
- View MRV status & CID trail  

### 💻 Web Dashboard (Community/NCCR Head)
- Project approval & verification  
- MRV review & acceptance  
- Audit CIDs & published evidence  
- Issue verifiable carbon credits  
- Download official MRV & certificate report  

### 🌐 Node.js Backend
- REST API for mobile & web
- Upload artifacts to IPFS  
- Trigger ML models (FastAPI)  
- Manage carbon certificate logic  
- Interact with smart contracts  

### 🤖 FastAPI Machine Learning Server
- NDVI & vegetation indices  
- Canopy segmentation & classification  
- Tree counting & density estimation  
- Biomass and carbon sequestration calculation  

### 🗄 IPFS Evidence Storage
- GeoJSON boundaries  
- Drone imagery  
- NDVI rasters & classified layers  
- Tree detection maps  
- Sensor logs  
- Registration & MRV JSON  

### ⛓ Polygon Smart Contract
- `registerProject()`  
- `updateMRV()`  
- Immutable MRV history  
- Public traceability via CIDs  

---

# 📊 Data Model

### 🔗 On-Chain Metadata
- `projectId`  
- `registrationCID`  
- `mrvCID`  
- `projectOwner`  
- `boundaryHash`  
- `verificationStatus`  
- `timestamps`  

### 📦 Off-Chain (Stored on IPFS)
- Drone images  
- GeoJSON boundary  
- NDVI + canopy maps  
- Tree detection maps  
- Sensor logs  
- `registration.json` & `mrv.json`  
- Carbon certificate (PDF)

---

# ⚙️ Configure Environment  
Configure API URLs, contract address, and IPFS gateway in environment files for both the backend and frontend.


# 🔄 Usage Flow

1. Field officer logs in via mobile app  
2. Creates a new project and draws the boundary on the map  
3. Uploads drone images and registration documents  
4. Backend stores files on IPFS and registers the project on-chain  
5. For MRV rounds, the officer uploads new drone data and triggers MRV  
6. ML server computes NDVI, canopy coverage, tree count, and carbon estimate  
7. Backend writes `mrv.json` to IPFS and updates the smart contract  
8. Verifiers and stakeholders trace every MRV record and underlying data via CIDs  

---

# 🎯 Key Benefits

- End-to-end digital MRV for blue carbon projects  
- Tamper-proof, transparent registry using blockchain  
- Verifiable linkage from carbon credits to raw drone and sensor data  
- Mobile-first workflow designed for field teams  
- Modular design (models, blockchain, or frontend can be swapped or extended)  


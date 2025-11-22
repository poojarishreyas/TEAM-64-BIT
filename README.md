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

# 📱 React Native Mobile App (Field Data Collection)

The React Native mobile application is designed for field officers, surveyors, and project developers working on mangrove and blue carbon restoration activities. It enables them to efficiently collect, upload, and verify ecological and geospatial data directly from the field.

### 🔧 Features
- **Secure Login & Identity**  
  Ensures authenticated access to project data using encrypted credentials.
  
- **Boundary Drawing on Map**  
  Officers can draw polygon boundaries to define the geographical extent of mangrove plantation or restoration zones.

- **Drone Data Upload**  
  The app allows uploading high-resolution drone imagery and registration documents as project evidence.

- **Sensor Data Capture**  
  Environmental measurements such as **pH, salinity, temperature, and humidity** can be uploaded along with geolocation, ensuring credible ecological assessment.

- **Trigger MRV Analysis**  
  Users can submit field data and request automatic ML-based MRV processing.

- **Track MRV & CID Trail**  
  Officers can monitor MRV status, review stored records, and access IPFS Content IDs (CIDs) linked to blockchain transactions.

---

# 💻 Web Dashboard (Community Head / NCCR Head)

The web dashboard acts as a governance and verification interface for government officials, community heads, and authorized verifiers such as **NCCR (National Centre for Coastal Research)**.

### ⚡ Key Capabilities
- **Project Approval & Verification**  
  Review project details, validate uploaded evidence, and approve or reject applications.

- **MRV Review & Acceptance**  
  Evaluate ML-generated outputs (NDVI, canopy cover, biomass estimates, etc.) before certification.

- **Audit IPFS CIDs**  
  Visibility into every stored artifact—drone images, GeoJSON, MRV JSON, evidence proofs, and more.

- **Issue Carbon Credits**  
  Generate blockchain-backed carbon credits once MRV is verified.

- **Download Official Reports**  
  Export verified MRV reports and blockchain-certified carbon credit documents.

---

# 🌐 Node.js Backend (Orchestration Layer)

The backend serves as the bridge between frontend clients (web/mobile), the machine learning server, IPFS storage, and blockchain smart contracts.

### 🔗 Responsibilities
- **REST API for Mobile & Web**  
  Centralized endpoints ensure secure and structured data flow.

- **Upload Evidence to IPFS**  
  Stores all files, logs, and processed outputs on distributed storage for immutability.

- **Trigger Machine Learning Workflow**  
  Sends drone and sensor data to FastAPI for NDVI, canopy, and biomass computation.

- **Carbon Certificate Logic**  
  Generates and manages verified MRV outputs before writing to blockchain.

- **Smart Contract Communication**  
  Publishes registration and MRV CID hashes to the Polygon network.

---

# 🤖 FastAPI Machine Learning Server

The ML engine performs advanced geospatial analysis and interprets ecological data to quantify mangrove carbon and biomass.

### 🧪 Core ML Functions
- **NDVI & Vegetation Indices**  
  Derives health and density metrics from drone imagery.

- **Canopy Classification**  
  Segments mangrove canopy areas and classifies species if required.

- **Tree Counting & Density**  
  Identifies tree clusters using object detection and spatial mapping models.

- **Biomass & Carbon Estimation**  
  Converts morphological characteristics into carbon sequestration estimates using scientific models.

---

# 🗄 IPFS Evidence Storage

All MRV-related assets are stored on **IPFS**, providing distributed integrity, transparency, and traceability.

### 📂 Stored Artifacts
- GeoJSON Project Boundaries  
- Raw Drone Imagery  
- NDVI Rasters & Classified Segments  
- Tree Detection Maps  
- Environmental Sensor Logs  
- `registration.json` & `mrv.json` files  
- Blockchain-backed Carbon Certificate (PDF)

Every artifact receives a unique **CID (Content Identifier)** linked to the blockchain.

---

# ⛓ Polygon Smart Contract (MRV Registry)

Smart contracts ensure traceability, immutability, and authenticity for carbon credit issuance.

### 💼 Contract Functions
- `registerProject()`  
  Stores initial registration metadata & CID references.

- `updateMRV()`  
  Publishes new MRV assessment as immutable blockchain history.

### 🔒 Guarantees
- Immutable MRV history  
- Publicly verifiable carbon accounting  
- Tamper-proof data via CID hashing  

---

# 📊 Data Model

### 🔗 On-Chain Metadata
Stored as lightweight hashes:
- `projectId`
- `registrationCID`
- `mrvCID`
- `projectOwner`
- `boundaryHash`
- `verificationStatus`
- `timestamps`

### 📦 Off-Chain (IPFS Artifacts)
- Drone Images  
- GeoJSON Boundary  
- NDVI & Canopy Maps  
- Tree Detection Maps  
- Sensor Readings  
- `registration.json`, `mrv.json`  
- Carbon Certificate PDF  

---

# ⚙️ Environment Configuration

Configure essential runtime variables in both **backend & frontend `.env`**:



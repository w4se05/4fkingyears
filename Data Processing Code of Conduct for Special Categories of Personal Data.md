# **I. PREAMBLE**

BioSecure Dynamics Ltd. ("the Company") focuses on developing and deploying biometric security solutions. These include access control systems, payment authentication, and security surveillance. Our goal is to provide seamless security for offices, banks, and government agencies.

As part of this work, the Company processes **Biometric Data**, specifically facial recognition profiles, fingerprint templates, and voiceprints. Under Article 9 of the General Data Protection Regulation (GDPR), this data is classified as a "Special Category of Personal Data." Unlike passwords or tokens, biometric data is tied directly to a person’s physical identity. It lasts indefinitely and cannot be reset if compromised.

This Code of Conduct ("the Code") provides the necessary framework for the ethical, legal, and secure processing of this data within our organization.

---

## **II. SCOPE OF APPLICATION**

### **1. Material Scope**

This Code applies to all activities involving biometric data processed by BioSecure Dynamics, whether through automated or manual methods. This includes:

**Collection:** Capturing raw biometric samples (e.g., scanning a face at a turnstile, recording a voice command).

**Processing:** Converting raw samples into digital templates (hashing) and comparing these templates against a database.

**Storage:** Keeping biometric templates on local servers, edge devices, or cloud infrastructure.

**Transfer:** Sending data between sensors, servers, and third-party clients.


### **2. Personal Scope (Who must follow this Code)**

**All Employees:** Every staff member, regardless of seniority, who designs, maintains, or accesses the systems that process biometric data.

**Contractors and Consultants:** External engineers, security personnel, and IT consultants hired by the Company.

**Third-Party Processors:** Vendors providing cloud storage, API services, or hardware maintenance. All these parties must sign a specialized Data Processing Agreement (DPA) that enforces the standards set by this Code.


### **3. Data Subject Scope (Whose data is protected)**

**End-Users:** Individuals using our systems for access (e.g., bank employees, office workers) or services (e.g., customers using biometric payment).

**Employees of BioSecure Dynamics:** Staff members who use internal biometric systems for secure access to facilities.

**The General Public:** Individuals who may be incidentally captured by security surveillance systems operated by the Company or its clients.


---

## **III. RIGHTS OF THE DATA SUBJECTS**

We recognize that data subjects fully own their biometric identity. The Company ensures the following rights, tailored to the context of biometric processing:

### **1. General Rights**

**Right to Transparent Information:** Data subjects must be informed through a clear Privacy Notice before any data collection occurs. This notice must convey the type of biometric data collected, the purpose (e.g., "security access"), and how long it will be kept.

**Right of Access:** Subjects have the right to know if their biometric data is being processed. Due to security risks, providing a copy of the raw biometric template is usually restricted, but the Company must give meaningful information about how the data is processed.

**Right to Rectification:** If a biometric template is wrongly linked to a profile (e.g., a fingerprint matches the wrong name), the subject has the right to correct it immediately.

**Right to Erasure ('Right to be Forgotten'):** Subjects can request the deletion of their biometric data when it is no longer needed for its original purpose or if they withdraw consent. Erasure means permanently destroying both the template and any backups.


### **2. Specific Rights in Biometric Cases**

**Right to Non-Biometric Alternatives:** In situations where there is an imbalance of power (e.g., Employer-Employee or Service Provider-Consumer), consent is not considered "freely given" if an alternative is not provided. Data subjects have the right to opt-out of biometric authentication for a secure alternative (e.g., RFID card, PIN, or mobile credential) without penalty or service denial.

**Right to Withdraw Consent:** When processing is based on consent (Article 9(2)(a)), the subject can withdraw it at any time. Once consent is withdrawn, the biometric template must be immediately removed from active verification systems.

**Right to Human Intervention:** If an automated decision (e.g., a facial recognition gate) denies access or a payment, the data subject can contest the decision and request immediate review by a human operator.


---

## **IV. POTENTIAL BREACH SCENARIOS**

Processing special category data involves significant risks. The Company identifies the following critical breach scenarios that this Code aims to prevent:

### **1. The "Honey-Pot" Database Breach**

**Scenario:** A malicious actor gains unauthorized access to the central server where biometric templates are stored.

**Risk:** If raw biometric images are stored, they can be stolen and used for identity theft. Even if only hashed templates are stored, skilled attackers may try to reverse-engineer them or use them in "replay attacks."


### **2. Presentation Attacks (Spoofing)**

**Scenario:** An attacker tries to bypass sensors using a high-resolution photograph, a video recording (deepfake), a 3D-printed mask, or a silicone fingerprint model.

**Risk:** Unauthorized access to high-security areas (offices, government buildings) or fraudulent financial transactions.


### **3. Interception and Replay Attacks**

**Scenario:** An attacker intercepts the data packet sent between the edge device (scanner) and the validation server.

**Risk:** The attacker can record the digital signal of the biometric template and "replay" it later to gain access, effectively cloning the user's digital presence without their physical body.


### **4. Function Creep**

**Scenario:** Biometric data collected for a specific security purpose (e.g., building entry) is used for unauthorized secondary purposes (e.g., employee time-tracking, performance monitoring, or marketing analytics) without fresh consent.

**Risk:** Violation of the Purpose Limitation principle, loss of trust, and serious legal penalties.


---

## **V. EXCEPTIONS AND CONDITIONS FOR APPLICATION**

Processing biometric data is generally forbidden under Article 9(1) of the GDPR, unless a specific exception applies. BioSecure Dynamics relies on the following legal bases:

### **1. Explicit Consent (Article 9(2)(a))**

This is the main basis for our commercial operations, including payment authentication and office access.

**Condition:** Consent must be explicit, affirmative, and recorded. A pre-ticked box or "implied" consent is not valid. The user must actively choose to join the biometric system.

**Revocability:** The user must be able to withdraw consent as easily as they granted it.


### **2. Employment and Social Security Obligations (Article 9(2)(b))**

**Exception:** This basis is used strictly for high-security internal zones (e.g., server rooms, R&D labs) where the Company is legally required to ensure maximum security for safety or data protection reasons.

**Condition:** This cannot be a blanket policy for all staff. It must be necessary and proportional to the specific risk of the area in question.


### **3. Substantial Public Interest (Article 9(2)(g))**

**Exception:** This applies when the Company provides systems to government agencies for national security, fraud prevention, or border control.

**Condition:** Processing must be based on clear Union or Member State law, which should be proportional to the aim pursued and include specific measures to protect the fundamental rights and interests of the data subject.


---

## **VI. MEASURES TO PREVENT VIOLATIONS**

To reduce the outlined risks and ensure strong compliance, BioSecure Dynamics requires the following technical and organizational measures.

### **1. Technical Security Measures**

**Prohibition on Raw Data Storage:** Storing raw biometric samples (e.g., .JPG of a face, .TIFF of a fingerprint) is strictly forbidden. The system must instantly convert the raw sample into a mathematical template (hash) and permanently delete the raw image.

**Template Protection (Salting and Encryption):** All biometric templates must be encrypted using industry-standard protocols (e.g., AES-256) when stored and transmitted. Templates must be "salted" (added random data) so that a compromised template from our database cannot be used to access other systems.

**Liveness Detection (PAD):** All sensors the Company uses must have Presentation Attack Detection (PAD) technology. This includes thermal sensing, 3D depth mapping, and blink detection to distinguish between a live person and a spoof (photo/mask).

**Cancelable Biometrics:** Where possible, the Company will use "cancelable biometric" algorithms that distort the biometric features in a repeatable way. If the data is compromised, a new "distortion" can be issued, effectively resetting the biometric password.


### **2. Organizational Measures**

**Data Protection Impact Assessment (DPIA):** A DPIA is required before developing or deploying any new biometric technology. This assessment must evaluate the necessity, proportionality, and risks to the rights and freedoms of data subjects.

**Strict Access Control (Role-Based Access):** Access to the database containing biometric templates is limited to the smallest number of authorized administrators needed for system maintenance. All access is logged and audited monthly.

**Vendor Compliance:** Any third-party hardware or software integrated into our systems must pass an ISO/IEC 27001 compliance review.

**Regular Penetration Testing:** The Company will hire certified ethical hackers every six months to attempt to breach our databases and spoof our sensors to find and fix vulnerabilities.


### **3. Data Breach Response**

**Immediate Action:** Any suspected breach of biometric data must be reported to the DPO within one hour of discovery.

**Notification:** Because of the high risk to rights and freedoms, the Company commits to notifying the relevant Supervisory Authority within 72 hours and informing affected data subjects quickly if their biometric templates are at risk.


---

## **VII. ENFORCEMENT**

Following this Code is a condition of employment and business partnership.

**Internal:** Employees found violating this Code will face disciplinary action, up to and including termination of employment and legal prosecution.

**External:** Partners found in violation will face immediate contract termination and liability for damages.
# Encrypto-secure-search-on-encrypted-data
Search on Encrypted Data**

```markdown
# 🔐 Secure Search on Encrypted Data with Privacy-Preserving Access Control

A privacy-preserving secure search system that enables **keyword search over encrypted documents** without exposing plaintext data to the server. The system ensures strong data confidentiality using AES encryption, RSA key protection, trapdoor-based search, and role-based access control.

---

# 🚀 Project Overview

This project implements a **secure searchable encryption system** where:

- Documents are encrypted before storage
- Server cannot read document contents
- Search happens using hashed trapdoors
- Decryption happens only on client side
- AES keys are protected using RSA
- Access control restricts document viewing

This solves the problem:

> **"Design a secure system that enables string matching on encrypted data while preserving confidentiality and privacy."**

---

# ⭐ Features

✅ Secure keyword search on encrypted data  
✅ Trapdoor-based privacy-preserving search  
✅ AES document encryption  
✅ RSA protected AES key  
✅ Client-side document decryption  
✅ Role-based access control (RBAC)  
✅ Identity authentication (IDP login)  
✅ Multi-word AND query support  
✅ No plaintext exposure to server  

---

# 🛡️ Security Layers (Defense in Depth)

## 1️⃣ Identity Authentication (IDP)
- Login required before access
- Session-based authentication

## 2️⃣ AES Document Encryption
- Documents encrypted using AES-128 CBC
- Server stores only encrypted files

## 3️⃣ Trapdoor-Based Secure Search
- Queries converted to SHA256 hashes
- Server never sees actual keywords

## 4️⃣ Role-Based Authorization
- Only admin can view documents

## 5️⃣ Client-Side Decryption
- Decryption happens in browser
- Server never sees plaintext

## 6️⃣ RSA Key Protection
- AES key encrypted using public key
- Only private key holder decrypts data

---

# 🏗️ System Architecture

```

User → Login → Query → Trapdoor Hash → Encrypted Index Search
→ Matching Encrypted Docs → Client Decrypts with Private Key

```

Server never accesses plaintext data.

---

# 📂 Project Structure

```

project/
│
├── app.py                  # Flask web application
├── preprocess.py           # Document preprocessing
├── build_index.py          # Trapdoor index generator
├── encrypt_docs.py         # AES document encryption
├── encrypt_aes_key.py      # RSA AES key encryption
├── requirements.txt
│
├── data/                   # Original documents
├── encrypted_docs/         # Encrypted documents
├── templates/              # HTML UI files
│
├── processed_data.json
├── encrypted_index.json
├── secret.key
├── encrypted_aes.key
├── public.pem
├── private.pem

````

---

# ⚙️ Installation & Setup

---

## 1️⃣ Clone Repository

```bash
git clone https://github.com/yourusername/secure-search-encrypted-data.git
cd secure-search-encrypted-data
````

---

## 2️⃣ Create Virtual Environment

```bash
python -m venv venv
venv\Scripts\activate
```

(Mac/Linux)

```bash
source venv/bin/activate
```

---

## 3️⃣ Install Dependencies

```bash
pip install -r requirements.txt
```

---

# 📊 System Setup Pipeline (IMPORTANT)

Run scripts in this exact order.

---

## STEP 1 — Add Documents

Place text files inside:

```
data/
```

---

## STEP 2 — Preprocess Documents

```bash
python preprocess.py
```

Creates:

```
processed_data.json
```

---

## STEP 3 — Build Secure Search Index

```bash
python build_index.py
```

Creates:

```
encrypted_index.json
```

---

## STEP 4 — Generate AES Secret Key (Run Once)

```python
from Crypto.Random import get_random_bytes

with open("secret.key","wb") as f:
    f.write(get_random_bytes(16))
```

---

## STEP 5 — Encrypt Documents

```bash
python encrypt_docs.py
```

Creates:

```
encrypted_docs/
```

---

## STEP 6 — Generate RSA Keys

```bash
python generate_keys.py
```

---

## STEP 7 — Encrypt AES Key with RSA

```bash
python encrypt_aes_key.py
```

Creates:

```
encrypted_aes.key
```

---

# ▶️ Running the Application

```bash
python app.py
```

Open browser:

```
http://127.0.0.1:5000
```

---

# 🔎 How Search Works

1. User logs in
2. User enters keyword
3. Query → SHA256 trapdoor
4. Server reveals matching encrypted docs
5. Client decrypts using private key
6. Plaintext never reaches server

---

# 👤 Default Login Credentials

```
Admin:
username: admin
password: admin123

User:
username: user
password: user123
```

---

# 🎯 Example Usage

```
Search: fever
→ System finds encrypted matches
→ Admin decrypts document locally
```

---

# ⚠️ Important Notes

* Server never stores plaintext
* Private key must remain secure
* Changing secret.key requires re-encryption
* RSA keys must match AES encryption step

---

# 🧪 Troubleshooting

## No results found

* Rebuild index
* Check secret key consistency

## Decryption failed

* Ensure correct private.pem
* Verify RSA encryption setup

## Key mismatch

* Re-run encryption pipeline

---

# 🔮 Future Improvements

* Homomorphic encryption search
* Secure multi-party computation
* Query embedding search
* Access anomaly detection
* Blockchain audit logs
* Zero knowledge authentication

---

# 📚 Technologies Used

* Python
* Flask
* AES Encryption
* RSA Cryptography
* SHA256 Hashing
* CryptoJS
* HTML/CSS/JS

---

# 📜 License

MIT License

---

# 👨‍💻 Author
Abhay Vadagi
Pavani N
Vishwamohan SN
Yeshrutha S

```


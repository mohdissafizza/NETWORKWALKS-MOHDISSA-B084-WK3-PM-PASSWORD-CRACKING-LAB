# 🔐 PDF Password Cracking & Cryptanalysis Lab

## 📌 Overview
This repository documents the practical execution, cryptanalysis, and verification of password cracking methodologies against encrypted Portable Document Format (PDF) files. Completed as part of the **Networkwalks Training Academy — Cybersecurity & Ethical Hacking** curriculum (**Week 3: Project Modules 1 & 2**), this lab demonstrates how weak passwords on legacy PDF encryption standards can be extracted and recovered via dictionary attacks.

---

## 🎯 Objectives
1. **Cryptographic Extraction:** Parse PDF trailer structures to extract standardized `$pdf$` cryptographic hashes (`pdf2john` format).
2. **Offline Hash Cracking (Module 1):** Configure and execute a dictionary attack using **John the Ripper (JTR Jumbo v1.9.0)** via the **Johnny GUI** front-end.
3. **Browser-Based Cryptanalysis (Module 2):** Extract hashes and perform client-side dictionary attacks using the **Networkwalks Security Tools** suite.
4. **Security Hardening:** Analyze password entropy weaknesses and propose enterprise remediation controls (AES-256 / NIST SP 800-63B).

---

## 🛠️ Tools & Environment
* **John the Ripper (Jumbo v1.9.0 - Win64):** Command-line password recovery engine.
* **Johnny GUI:** Cross-platform graphical front-end for John the Ripper.
* **Networkwalks Security Suite:** Client-side Web Crypto Hash Calculator & Dictionary Attack Engine.
* **Target Standard:** Adobe PDF Revision 4 / Version 4 (128-bit RC4/AES Standard Security Handler).

---

## 📊 Summary of Lab Findings

| Parameter | Module 1: JTR & Johnny GUI | Module 2: Networkwalks Web Suite |
| :--- | :--- | :--- |
| **Target File** | `My Locked PDF1.pdf` | `My-Locked-PDF1.pdf` (65.2 KB) |
| **Encryption Standard** | PDF Rev 4 / Ver 4 (128-bit) | PDF Rev 4 / Ver 4 (128-bit) |
| **Extraction Tool** | Online `pdf2john` Hash Extractor | Networkwalks Hash Calculator |
| **Attack Method** | Dictionary Attack (Default Wordlist) | Built-in Wordlist Attack (100 words) |
| **Performance** | `< 1 second` | `9 pw/s` (Cracked at attempt `91/100`) |
| **Recovered Password** | `good-luck` | `password1` |
| **Status** | ✅ Decrypted & Verified | ✅ Decrypted & Verified |

---

## 💻 Execution & Proof of Concept

### Module 1: Execution & Proof of Concept

<img width="975" height="710" alt="image" src="https://github.com/user-attachments/assets/03245441-be52-40dd-a69a-4ad537ba6710" />
<img width="975" height="761" alt="image" src="https://github.com/user-attachments/assets/8ba53f00-e238-4540-aed4-9920ffd2da5b" />
<img width="760" height="1059" alt="image" src="https://github.com/user-attachments/assets/08192d4f-8a69-468f-9e16-fea4239c0c84" />

---

### Module 2: Execution & Proof of Concept

<img width="975" height="611" alt="image" src="https://github.com/user-attachments/assets/5afc8c5e-5925-4133-8178-060c5c15b098" />
<img width="975" height="765" alt="image" src="https://github.com/user-attachments/assets/6ae95228-b0be-4f28-82ea-1c6d8fdf3483" />
<img width="806" height="1034" alt="image" src="https://github.com/user-attachments/assets/13f79b6e-12e2-48ca-b903-cb094618b507" />

---

## 🛡️ Key Security Takeaways & Remediation
1. **Upgrade to PDF 2.0 (ISO 32000-2):** Deprecate PDF Revision 4 (128-bit) in favor of **Revision 6 (256-bit AES)**, which utilizes iterative SHA-256/512 key derivation to resist offline brute-force and dictionary attacks.
2. **Enforce High-Entropy Passphrases:** Follow **NIST SP 800-63B** guidelines by requiring multi-word passphrases of at least 16 characters rather than single dictionary words with simple digit suffixes.
3. **Implement Information Rights Management (IRM):** Replace static file passwords with identity-based access controls (e.g., Microsoft Purview Information Protection) that enforce MFA and dynamic access revocation.

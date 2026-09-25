# Zuhairhussyn-NETWORKWALKS-ZUHAIR_HUSSAIN-B083-WK3-Cybersecuirty-Lab

# Password Cracking with JTR & Networkwalks Tools

Cybersecurity & Ethical Hacking project — Week 3 lab tasks (Networkwalks Academy).

This project demonstrates password recovery on password-protected PDF files using two different approaches: the industry-standard **John the Ripper (JTR)** suite, and **Networkwalks' own browser-based Hash Calculator + Password Cracker tools**. The goal was to understand, hands-on, how password hashes are extracted from protected files and how dictionary attacks work — and to see firsthand why weak passwords fall in seconds.

> ⚠️ **Disclaimer:** This is an educational lab exercise performed on sample files provided by the course, in a controlled environment. Password cracking should only ever be performed on files/systems you own or have explicit authorization to test.

---

## Tools Used

| Tool | Purpose |
|---|---|
| [John the Ripper (JTR)](https://www.openwall.com/john/) | CLI password-cracking engine |
| [Johnny](https://openwall.info/wiki/john/johnny) | GUI front-end for John the Ripper |
| [Networkwalks Hash Calculator](https://networkwalks.com/hash-calculator/) | Extracts a crackable hash from a password-protected PDF, in-browser |
| [Networkwalks Password Cracker](https://networkwalks.com/password-cracker/) | Runs a dictionary attack against a hash, in-browser |

---

## Module 1: Password Cracking with JTR (John + Johnny)

**Task:** Crack the password of 3 locked PDF files using JTR John and JTR Johnny.

### Process

1. **Setup** — Downloaded John the Ripper (jumbo build) and Johnny GUI for Windows. Linked Johnny to `john.exe` under Settings.

  <img width="970" height="545" alt="Johnny_setup" src="https://github.com/user-attachments/assets/f79d073d-62a8-4729-95ca-09bb0e4d4bb0" />

2. **Hash extraction** — For each locked PDF, extracted the password hash (format: `$pdf$...`) using the Hash Calculator.

   [hash1.txt](https://github.com/user-attachments/files/32672268/hash1.txt)
   [hash2.txt](https://github.com/user-attachments/files/32672271/hash2.txt)
   [hash3.txt](https://github.com/user-attachments/files/32672277/hash3.txt)

3. **Cracking in Johnny** — Opened each hash file in Johnny via **Open password file → Open other file format (*2john) → PASSWD format**, then ran **Start new attack**.

4. **Results:**
    are shown below:

   <img width="940" height="639" alt="PM1_PDF1_cracked_result" src="https://github.com/user-attachments/assets/ea2b0f87-1dc6-4895-bfac-6059263081ba" />
   <img width="1069" height="661" alt="PM1_PDF2_cracked_result" src="https://github.com/user-attachments/assets/a246af75-d683-472f-bfb1-e3e70d6db7d3" />
   <img width="975" height="682" alt="PM1_PDF3_cracked_reult" src="https://github.com/user-attachments/assets/fb059461-ab9a-40b4-9e0b-5342c1bc42a5" />

5. **Verification** — Opened each PDF with its recovered password to confirm access as shown in Results.

---

## Module 2: Password Cracking with Networkwalks Tools

**Task:** Crack the same 3 PDF files using Networkwalks' own Hash Calculator + Password Cracker (browser-based, no install required).

### Process

1. Uploaded each locked PDF to the **Hash Calculator** to extract its `$pdf$...` hash.
2. Pasted the hash into the **Password Cracker**, ran the built-in wordlist attack.
3. Recorded the cracked password for each file.

### Results

<img width="864" height="565" alt="PM2_PDF1_result" src="https://github.com/user-attachments/assets/0cb97f60-cd0f-4028-9501-036ff2705510" />
<img width="849" height="420" alt="PM2_PDF2_result" src="https://github.com/user-attachments/assets/e3a8e870-9676-43e1-9a9c-a3c3e4644942" />
<img width="1040" height="672" alt="PM2_PDF3_result" src="https://github.com/user-attachments/assets/d3910b21-7b72-4d51-97df-87940517c1db" />

---

## Key Takeaways

- **Encryption vs. Hashing:** A PDFs password isn't saved in plain text. Instead the password is stored as a hash. Tools that crack these passwords don't decrypt anything directly. They generate hashes from passwords and compare them to the hash stored in the file.

- **Weak passwords crack instantly.** Passwords like `password1` were broken in less than a second using a list of common words.

- **Stronger passwords take time.** One PDF with a complex password took between 10 and 15 minutes to crack even with a dictionary attack. This shows how important strong passwords really are.

- ** Underlying process, two interfaces.** Both JTR/Johnny and the Networkwalks web tools use the same method: extract the hash then run a dictionary attack. The difference is only in, how you access it.

---

## Reference

Lab guides and background material: [networkwalks.com](https://www.networkwalks.com)

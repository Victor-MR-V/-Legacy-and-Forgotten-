# -Legacy-and-Forgotten-
# CTF Writeup: Legacy and Forgotten

## Challenge Details
- Challenge Name: Legacy and Forgotten
- Points: 296
- Category: OSINT / Reconnaissance / CVE Research
- Flag Format: `PCSIP{cve-yyyy-nnnn_edb-nnnnn}`

---

## Challenge Description
"A routine internal sweep turned up a box nobody remembers deploying. IT has no ticket for it. Before anyone touches it, we need to know exactly what we're dealing with - starting with that oddly old FTP service. This challenge requires REAL reconnaissance: search a public CVE database, Exploit-DB, or use searchsploit to research the exact software version in the scan report. Nothing needed to solve this is hidden in the provided file - it's all in the report AND on the public internet."

---

## My Solution

### 1. Analyzing the Clues
The challenge asks us to investigate an old, forgotten FTP service found in a scan report. It explicitly guides us to use public vulnerability databases like Exploit-DB or CVE databases to find the correct identifiers for this specific exploit.

### 2. Reconnaissance & Research
By looking at the provided scan report file, I identified the exact software and version of the outdated FTP service running on the box (which was `vsftpd 2.3.4`). 

I searched public exploit databases and `searchsploit` for this version to look up its historical backdoor vulnerability. The research provided the two required unique identifiers:
- **CVE ID:** `CVE-2011-2523`
- **Exploit-DB ID (EDB-ID):** `49757`

### 3. Constructing the Flag
The challenge requires the flag format to be lowercase and structured as `PCSIP{cve-yyyy-nnnn_edb-nnnnn}`. 

Converting the discovered IDs to lowercase and inserting them into the template gives the final flag.

## Flag
```text
PCSIP{cve-2011-2523_edb-49757}
```

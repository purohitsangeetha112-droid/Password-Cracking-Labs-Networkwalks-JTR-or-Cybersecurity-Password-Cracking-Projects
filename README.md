# Comprehensive Guide to Password Cracking: Networkwalks Tools & John the Ripper

## Table of Contents

1. [Overview](#overview)
2. [Lab 1: Password Cracking with Networkwalks Tools](#lab-1-password-cracking-with-networkwalks-tools)

   * [Objective](#objective-1)
   * [Tools Used](#tools-used-1)
   * [Methodology](#methodology-1)
   * [Outcome](#outcome-1)
3. [Lab 2: Password Cracking with John the Ripper](#lab-2-password-cracking-with-john-the-ripper)

   * [Objective](#objective-2)
   * [Tools Used](#tools-used-2)
   * [Methodology](#methodology-2)
   * [Outcome](#outcome-2)
4. [Theoretical Concepts & Key Takeaways](#theoretical-concepts--key-takeaways)
5. [Password Attack Techniques](#password-attack-techniques)
6. [Importance of Strong Passwords](#importance-of-strong-passwords)
7. [Real-World Context](#real-world-context)
8. [Skills Learned](#skills-learned)
9. [Conclusion](#conclusion)
10. [Disclaimer](#disclaimer)

---

# Overview

This repository documents two practical cybersecurity laboratory exercises focused on **password recovery, password cracking concepts, hash extraction, and password security**.

The purpose of these labs is not to gain unauthorized access to systems or files. Instead, they demonstrate how password-cracking tools work in a **controlled and authorized cybersecurity training environment**.

Two different approaches were explored:

1. **Networkwalks web-based password-cracking tools**
2. **John the Ripper (JTR) with the Johnny graphical interface**

Both exercises used the same password-protected PDF file, `My Locked PDF1.pdf`, which was provided specifically for the laboratory exercise.

The practical workflow demonstrated an important cybersecurity concept:

```text
Password-Protected File
        ↓
Hash Extraction
        ↓
Hash Preparation
        ↓
Password-Cracking Attempt
        ↓
Password Recovery
        ↓
Password Verification
```

The recovered password in the laboratory exercise was:

```text
password1
```

The exercise also demonstrated why simple and commonly used passwords should be avoided.

---

# Lab 1: Password Cracking with Networkwalks Tools

## Objective

The objective of this laboratory was to understand how a password-protected PDF can be analyzed and how its password-protection information can be converted into a format that password-cracking tools can process.

The exercise involved extracting a crackable `$pdf$` hash and performing a dictionary-based password recovery attempt using the Networkwalks tools provided as part of the training environment.

---

## Tools Used

* **Networkwalks Hash Calculator** – Used to extract password-related hash information from the protected PDF.
* **Networkwalks Password Cracker** – Used to perform the dictionary-based password recovery attempt.
* **Web Browser** – Used to access the laboratory tools.
* **PDF Reader** – Used to verify whether the recovered password successfully opened the protected document.

---

## Methodology

### Step 1: Obtain the Protected PDF

The encrypted PDF file:

```text
My Locked PDF1.pdf
```

was obtained from the authorized laboratory environment.

The file was password protected, meaning its contents could not be accessed without providing the correct password.

---

### Step 2: Extract the PDF Hash

The Networkwalks Hash Calculator was opened in a web browser.

The PDF was uploaded through the appropriate **PDF** option. The tool analyzed the document and generated a `$pdf$` formatted hash.

The extracted hash contained information related to the PDF's password-protection mechanism, including its revision and encryption parameters.

The generated value was copied carefully because even a missing or modified character could cause the cracking tool to reject the hash.

---

### Step 3: Prepare the Hash

The complete `$pdf$` hash was copied from the hash calculator.

The hash was checked to ensure that:

* The `$pdf$` prefix was present.
* No characters were accidentally removed.
* No unnecessary spaces were added.
* The complete hash was copied.

Correct hash formatting is important because cracking software expects the input to follow a particular structure.

---

### Step 4: Perform the Dictionary Attack

The Networkwalks Password Cracker was opened.

The extracted hash was entered into the appropriate field.

A built-in dictionary containing commonly used passwords was selected. The tool then tested candidate passwords against the target hash.

The basic concept can be represented as:

```text
Dictionary
    ↓
Candidate Password
    ↓
Password Verification Process
    ↓
Compare With Target
    ↓
Match?
  /     \
Yes      No
 ↓       ↓
Found   Try Next
```

---

### Step 5: Verify the Result

The cracking process successfully identified the password as:

```text
password1
```

The recovered password was then used to open the protected PDF.

Successful opening of the document confirmed that the recovered password was correct.

---

## Outcome

The Networkwalks tools successfully recovered the password:

```text
password1
```

This demonstrated how a **dictionary attack** can be effective against weak and commonly used passwords.

The main lesson from this exercise is that password complexity and uniqueness are important security controls. A password that appears in common password dictionaries can potentially be recovered much faster than a strong, unique passphrase.

---

# Lab 2: Password Cracking with John the Ripper

## Objective

The objective of the second laboratory was to understand how **John the Ripper (JTR)** can be used for password-recovery testing against a password-protected PDF in an authorized laboratory environment.

This exercise also provided practical experience with:

* Installing John the Ripper
* Preparing a compatible hash file
* Configuring the Johnny GUI
* Loading a password hash
* Starting a password-recovery attack
* Verifying the recovered password

---

## Tools Used

### John the Ripper

John the Ripper is an open-source password-security auditing and password-recovery tool commonly used by cybersecurity professionals to test password strength.

### Johnny

Johnny is a graphical user interface for John the Ripper. It provides a more user-friendly way to configure and operate JTR.

### PDF Hash Extraction Tool

An authorized PDF hash extraction service was used to convert the protected PDF into a format that could be processed by John the Ripper.

### PDF Reader

A PDF reader was used to verify the recovered password.

---

# Methodology

## Step 1: Install John the Ripper

John the Ripper and the Johnny graphical interface were installed on the Windows laboratory system.

The installation provided the JTR core executable required by Johnny.

Depending on the distribution, the executable may be located in the John installation directory and may use a filename such as:

```text
john.exe
```

or an enhanced Jumbo build executable.

---

## Step 2: Extract the PDF Hash

The protected PDF was processed using the PDF hash-extraction tool.

The resulting output contained a `$pdf$` formatted hash.

The purpose of this step was to convert the password-protected PDF into a representation that John the Ripper could process.

---

## Step 3: Prepare the Hash File

The extracted hash was copied into a plain-text file.

For example:

```text
hash1.txt
```

A critical part of this process was checking the beginning of the extracted value.

The hash needed to begin with:

```text
$pdf$
```

Sometimes copied output may contain additional characters such as:

```text
b'
```

or quotation marks.

These unnecessary characters can prevent the cracking software from correctly recognizing the hash format, so the hash file was cleaned before use.

The final text file contained the appropriate `$pdf$` hash value.

---

## Step 4: Configure Johnny

The Johnny GUI was opened.

The application was configured to use the John the Ripper executable installed on the system.

The executable path was selected through the **Settings** section.

This configuration allowed Johnny to communicate with the underlying JTR engine.

---

## Step 5: Load the Hash File

The **Open Password File** option was selected.

The prepared file:

```text
hash1.txt
```

was loaded into Johnny.

The interface then displayed the hash information available for the password-recovery operation.

---

## Step 6: Start the Attack

The appropriate attack option was selected and the password-recovery process was started.

John the Ripper tested candidate passwords against the supplied hash.

Conceptually, the process can be represented as:

```text
Candidate Password
        ↓
Password Processing
        ↓
Compare With Target Hash
        ↓
     Match?
     /     \
   Yes      No
    ↓        ↓
Password   Continue
 Found     Testing
```

The exact speed of password recovery depends on several factors, including:

* Password complexity
* Password length
* Hashing/encryption algorithm
* Hardware performance
* Attack method
* Candidate-password list
* Configuration of the cracking tool

---

## Step 7: Verify the Password

After the password-recovery process completed, Johnny displayed the recovered password:

```text
password1
```

The password was then used to open the original PDF.

The document opened successfully, confirming that the recovered password was correct.

---

# Outcome

John the Ripper successfully recovered the password used for the laboratory PDF:

```text
password1
```

This demonstrated that different password-recovery tools can process the same password-protected file when the appropriate hash format is available.

The exercise also provided practical experience with the relationship between:

```text
Protected File
      ↓
Extracted Hash
      ↓
Hash File
      ↓
Password-Recovery Tool
      ↓
Candidate Password
      ↓
Verification
```

---

# Theoretical Concepts & Key Takeaways

## 1. Encryption vs. Hashing

Encryption and hashing are different security concepts.

### Encryption

Encryption is generally a **reversible process**.

Plaintext is transformed into ciphertext using an encryption mechanism and a key.

```text
Plaintext
    ↓
Encryption + Key
    ↓
Ciphertext
```

With the appropriate key, the encrypted information can be decrypted.

Encryption is primarily used to provide confidentiality for data.

---

### Hashing

Hashing is designed as a **one-way transformation**.

Data is processed through a hash function to produce a fixed-format digest.

```text
Input Data
    ↓
Hash Function
    ↓
Hash Value
```

A secure cryptographic hash is designed so that recovering the original input from the hash is computationally difficult.

Hashing is commonly used for:

* Integrity verification
* Password storage
* Digital signatures
* File identification
* Security applications

---

## 2. Password Cracking

Password cracking refers to systematically testing possible passwords to determine whether one corresponds to the target password representation.

The process does not necessarily mean "decrypting" the password.

For a dictionary attack, the general concept is:

```text
Password Dictionary
        ↓
Candidate Passwords
        ↓
Verification / Hash Processing
        ↓
Comparison
        ↓
Matching Candidate
```

If a candidate produces the expected result, the corresponding password may have been identified.

---

# 3. Dictionary Attack

A dictionary attack uses a predefined collection of commonly used or likely passwords.

For example, a dictionary might contain entries such as:

```text
password
password1
admin
welcome
qwerty
123456
```

If the target password is included in the dictionary, the attack may find it quickly.

This is why passwords based on common words, names, predictable patterns, or simple number combinations are considered weak.

---

# 4. Brute-Force Attack

A brute-force attack systematically attempts combinations from a defined character set.

For example:

```text
a
b
c
...
aa
ab
ac
...
aaa
aab
...
```

As password length and character variety increase, the number of possible combinations can increase dramatically.

Therefore, password length is an important factor in resistance to guessing attacks.

---

# 5. Hybrid and Rule-Based Attacks

Modern password-auditing tools can also use more advanced strategies.

A rule-based approach can modify dictionary words by applying common patterns.

For example:

```text
password
password1
Password1
password123
Password@123
```

This demonstrates why simply adding a number or changing capitalization may not provide as much protection as creating a genuinely unique passphrase.

---

# Importance of Strong Passwords

The laboratory password:

```text
password1
```

is an example of a predictable password structure.

It consists of a common word followed by a simple number.

Such patterns are commonly tested by password-auditing tools.

A stronger password strategy should focus on:

* Greater length
* Uniqueness
* Avoiding common words
* Avoiding personal information
* Avoiding predictable substitutions
* Using a password manager where appropriate
* Enabling multi-factor authentication (MFA)

For example, instead of relying on a short predictable password, users can use a long, unique passphrase or a randomly generated password.

---

# Real-World Context

Password security remains an important part of cybersecurity because compromised credentials can contribute to unauthorized access to accounts and services.

Credential-related attacks can involve:

* Password reuse
* Credential stuffing
* Phishing
* Password spraying
* Brute-force attempts
* Dictionary attacks
* Previously leaked credentials

Large collections of previously exposed credentials can also make reused passwords particularly risky.

This means that password security should not depend only on making a password "hard to guess."

A broader security strategy should include:

```text
Strong Password
      +
Unique Password
      +
Multi-Factor Authentication
      +
Secure Password Storage
      +
Monitoring
      +
User Awareness
```

---

# Skills Learned

These laboratory exercises provided practical exposure to several cybersecurity concepts.

### Technical Skills

* Understanding password-protected files
* Understanding hash extraction
* Recognizing `$pdf$` hash formats
* Preparing hash files
* Using dictionary-based password recovery
* Working with John the Ripper
* Using the Johnny GUI
* Understanding basic password-attack workflows
* Verifying recovered credentials in an authorized environment

### Cybersecurity Concepts

The exercises also helped develop an understanding of:

* Password security
* Hashing
* Encryption
* Dictionary attacks
* Brute-force attacks
* Password complexity
* Credential security
* Security auditing
* Defensive password policies

---

# Key Learning

The most important lesson from these exercises is that **password security is not only about keeping a password secret; it is also about making the password difficult to guess or recover**.

A weak password may be exposed through relatively simple password-auditing techniques.

Security professionals can use tools such as John the Ripper in authorized environments to identify weak credentials and recommend stronger security controls.

The goal of password auditing should therefore be:

```text
Identify Weakness
       ↓
Understand Risk
       ↓
Improve Password Policy
       ↓
Implement Strong Authentication
       ↓
Reduce Credential-Based Risk
```

---

# Conclusion

These two laboratory exercises provided practical experience with password-recovery concepts using both web-based tools and John the Ripper.

The first laboratory demonstrated how a protected PDF could be processed through a web-based hash calculator and password-cracking tool.

The second laboratory demonstrated how the same type of password-protection information could be prepared as a hash file and processed using John the Ripper through the Johnny GUI.

Both exercises resulted in the recovery of the laboratory password:

```text
password1
```

The practical results reinforced the importance of using long, unique passwords and additional authentication mechanisms such as multi-factor authentication.

For cybersecurity professionals, understanding password-cracking techniques is valuable because the same knowledge can be applied defensively to:

* Audit password policies
* Identify weak authentication practices
* Improve credential security
* Educate users
* Strengthen organizational security controls

The purpose of learning these techniques is ultimately to **understand how password attacks work so that stronger defenses can be designed and implemented.**

---

# Disclaimer

> **Educational and Authorized Use Only**
>
> This repository is intended strictly for educational, academic, and authorized cybersecurity training purposes.
>
> All password-recovery activities documented in this repository were performed in a controlled laboratory environment using files specifically provided for training.
>
> Password-cracking tools such as John the Ripper should only be used against systems, files, accounts, or credentials for which explicit authorization has been provided.
>
> Attempting to access, recover, or crack passwords belonging to another person or organization without authorization may violate applicable laws and regulations.
>
> The author does not support unauthorized access, credential theft, privacy violations, or malicious use of cybersecurity tools.
>
> Always obtain appropriate permission before conducting security testing or password auditing.

---

## Final Takeaway

```text
Weak Password
      ↓
Easier to Guess
      ↓
Higher Credential Risk
      ↓
Potential Unauthorized Access

Strong + Unique Password
      +
MFA
      +
Secure Authentication Practices
      ↓
Better Account Security
```

**Learn the attack. Understand the weakness. Build the defense.**
EVIDENCE:<img width="1920" height="1020" alt="Screenshot 2026-09-28 153405" src="https://github.com/user-attachments/assets/a529ff12-f9e8-4037-a02e-7706bf0a8ca9" />
<img width="1920" height="1020" alt="Screenshot 2026-09-28 153412" src="https://github.com/user-attachments/assets/fd87f294-4800-4e06-84a3-74d3edca9e78" />
<img width="1920" height="1020" alt="Screenshot 2026-09-28 153426" src="https://github.com/user-attachments/assets/6e36edfc-641c-4f94-9055-d24b446159fd" />
<img width="1920" height="1020" alt="Screenshot 2026-09-28 153614" src="https://github.com/user-attachments/assets/5167eb13-4b6b-4a1e-a6b7-03ed8d9be36e" />
<img width="1920" height="1020" alt="Screenshot 2026-09-28 153645" src="https://github.com/user-attachments/assets/9619d18a-04e3-4227-a25d-a3bb7ce2cd8b" />
<img width="1920" height="1020" alt="Screenshot 2026-09-28 153858" src="https://github.com/user-attachments/assets/988f90b0-167c-4a9e-b352-d5ff3d2bd1ef" />


---
title: Computer System Security
teacher: Muleta Taye
e-mail: muleta.taye@aastu.edu.et
---
# CH 1: Introduction
**System** is a conceptual framework to interrelate elements.
- a set of interrelated elements that operate collectively to accomplish some common purpose or goal.
- Systems can be:
	1. **abstract**: orderly arrangement of interdependent *ideas or constructs*.
	2. **physical**: an arrangement of physically existed entity. e.g. a computer system

**Security** - measures and controls that ensure confidentiality, integrity, and availability of information system assets.
- ”is the protection as well as maintenance of the level of acceptable risk”

**Terminologies** 
*Computer Security*: can focus on ensuring the availability and correct operation of a computer
system without concern for the information stored or processed by the computer.
*Information Security*: is concerned with the *confidentiality*, *integrity* and *availability* of data regardless of the form the data may take: electronic, print, or other forms.
- about protecting data attributes., Preventing unauthorized access or modification.
*Information assurance*: assuring information and managing risks related to its use, processing,
storage, and transmission of information or data and the systems and processes used for those purposes. - building trust and managing risk. (Managing the lifecycle of information)
*Network Security*: protecting the Communication Infrastructure.
*Data Security*: 1. Where is it stored? 2. Who uses it? 2. How is it protected?
*Application Security*:  protecting software applications and systems against vulnerabilities and malicious attacks.
*Endpoint Security*: protect individual devices
*Security Incident Response*: developing and implementing procedures to handle security incidents.
*Security Awareness and Training* 

**Risk** is anything that may *damage* your computing *assets* without your knowledge or consent.
- Or potential security threat to exploit a vulnerability - MAY CAUSE A SERIOUS PROBLEM -Expectation of loss.
*Causes:* 
1. *Trust* - It is the likelihood that people will act the way you expect them to act.
	- in computer sec. - ”the level of confidence that we have in a computer system or its components to behave as expected”
	- Trust may be
	1. Most Trusted: internal servers, domain controllers, and storage devices attached to the network. why?
	2. Less trusted (not most trusted)
		- include internal users and remote, authenticated users.
		- why users less trusted then? Minority that abuses its privileges.
	3. Least trusted (un-trusted):
		- Internet servers and remote, unauthenticated users.
		- Can you trust Internet Server ? NEVER

2. *Weaknesses and Vulnerabilities*	- Any flaws or gaps in a system’s security that could be exploited by attackers.
	- *External Weakness* → malware, spyware, hackers, crackers, and script kiddies.
	- *Internal Weakness* → not all attacks come from outside. e.g. Authenticated Users, Unauthorized Programs, Un-patched Software
	- *Vulnerabilities* 

### Security Objectives
Responsibility of Security professionals is Protecting their environments as effectively as possible.

**CIA** 
1. *Confidentiality*: Ensure that no data is disclosed intentionally or unintentionally.
	- Covers two related concepts 
		- *Data confidentiality* - Assures that private or confidential information is not made available or disclosed to unauthorized individuals.
		- *Privacy* - its a way of controlling individual information.
2. *Integrity*: Ensure that data is not modified by an unauthorized personnel.
	- The data remains consistent, both internally and externally.
	- overs two related concepts:
		- *Data integrity*: Assures that information and programs are changed only in a specified and authorized manner.
		- *System integrity*: Assures that a system performs as intended in an unimpaired manner, free from deliberate or inadvertent unauthorized manipulation of the system.
3. *Availability*: Assures that systems work promptly and service is not denied to authorized users.

	additionally no.4
4. *Non-Repudiation*: To ensure that the sender cannot deny having created and sent the message (typically achieved via mechanisms like digital signatures).

*Contradicting Goals (Opposite of CIA)* 
- Disclosure,
- Alteration, and
- Denial

**Terminologies** 
- *Adversary* (threat agent) - An entity that attacks, or is a threat to, a system.
- *Attack*: Any kind of malicious activity that attempts to collect, disrupt, deny, degrade, or destroy information system resources or the information itself.
	- 2 kind
		- *Active attack*: attempts to alter system resources or affect their operation.
		- *Passive attack*: attempts to learn or make use of information from the system but does not affect system resources
	- Based on the Origin
		- Inside attack:
		- Outside attack:
- *Countermeasure* - An action, device, procedure, or technique that reduces a threat, a vulnerability, or an attack. (before an attack)
- *Risk* - An expectation of loss expressed as the probability that a particular threat will exploit a particular vulnerability with a particular harmful result.
- *Security Policy* - A set of rules and practices that specify how a system or org provides security services to protect sensitive and critical system resources.
- *System Resource* - Any Computing infrastructure/Assets. Threat - A potential aspects for violation of security.
- *Vulnerability* - Flaw or weakness in a system’s design, implementation, or operation and management that could be exploited to violate the system’s security policy.

# CH 2: Threats and Responses
### Threats
**Threat** is a potential violation of security in computing infrastructure OR
- anything that has the potential to disrupt/disturb or do harm to an organization.
- A Threat represents a potential security harm to an asset

There are three major types of threats:
- *Natural threats*: acts of nature that can be unpredictable in terms of onset, duration and impact.
- *Intentional*: deliberately to Compromise the entire computing system. (e.g. Crackers)
- *Unintentional*: Accidental or Unintended, oftentimes be attributed to human error.

**Attack** is a threat that is being carried out.
- if successful it leads to an undesirable violation of security.

2 Flavors:
1. *Active attack*: attempt to alter system resource or affect their operations
2. *Passive attack*: attempt to learn or make use of information from the system.

2 types based on the origin of the attack
1. *Inside attack*: Initiated by an entity inside the security perimeter (an “insider”).
	- The insider is authorized to access system resources but uses them in a way not approved by those who granted the authorization.
2. *Outside attack*: Initiated from outside the perimeter, by an unauthorized or illegitimate user of the system (an “outsider”).

RFC 4949, describes four diﬀerent type of threats
1. ***Unauthorized disclosure*** - an intruder gains access to data for which they are not authorized.
	- is a confidentiality threat.
	- Attacks:
		- *Exposure* - sensitive data released to unauthorized entity.
		- *Interception* - unauthorized entity directly accesses sensitive data in communication channels.
		- *Inference* - an unauthorized entity indirectly accessing sensitive data by reasoning from characteristics or by-product of communications.
		- *Intrusion* - an authorized entity circumvents system's security protections.

2. ***Deception*** - results in an authorized entity receiving false data and believing it to be true.
	- Attacks as a result of deception
		- *Falsiﬁcation*: False data deceive an authorized entity.
		- *Repudiation*: An entity deceives another by falsely denying responsibility for an act.
		- *Masquerade*: An unauthorized entity gains access to a system or performs a malicious act by posing as an authorized entity.

3. ***Disruption*** - A circumstance that interrupts or prevents the correct operation of system services and functions.
	- Attacks:
		- *Incapacitation*: Prevents or interrupts system operation by disabling a system component.
		- *Corruption*: Undesirably alters system operation by adversely modifying system functions or data.
		- *Obstruction*: interrupts delivery of system services by hindering system.

4. *Usurpation* - is a threat to system integrity.
	- Attacks:
		- *Misappropriation*: An entity assumes unauthorized logical or physical control of a system resource. (ownership of resource)
		- *Misuse*: occur by means of either malicious logic or a hacker that has gained unauthorized access to a system. (use of resource)


**TOP CYBER THREATS** 
1. **Malware**
	1. *Ransomware*: is malware designed to use encryption to force the target of the attack to pay a ransom demand.
		- it encrypts the User’s ﬁles and demands payment in exchange for the decryption key.
	2. *Crypto miners*: Malware that uses the victim’s machine to mine cryptocurrency and make a proﬁt for the attacker
	3.  *Mobile Malware*: Malware targeting mobile devices, including malicious applications and attacks exploiting SMS and social media apps.
	 4. *Info-stealers*: Malware that collects sensitive information from an infected computer and sends it to the malware operator.
	 5. *Banking Trojans*: Malware that speciﬁcally targets ﬁnancial information.

2. **Phishing** 
	- Trick a user into clicking on a malicious link, to locate and exploit a vulnerability.
	- Stealing Conﬁdential Information, Harvesting Login Information, Impersonating
	- Types: Regular phishing, Spear phishing, Smishing and vishing, Whaling

3. **Man-in-the-Middle(MitM)**: is a general term for when a intruders positions themselves in a conversation between a user and an application.
	- To either to eavesdrop or to impersonate one of the parties.

4. **Cyber Vandalism**: Involves editing online content in a malicious manner.
	- It involves adding or removing or modifying content which is oﬀensive or is in bad taste!

5. **Web Jacking**: Attackers create a fake website and when the website opens it will direct it to another website and harm the user’s system. OR
	- is the forceful control of a web server through gaining access and control over the website.

6. **Password Attack**: Any attempt to obtain or decrypt user’s password for illegal access.
	1. Brute-Force-Attacks
	2. Dictionary Attacks
	3. Key-Logger Attacks

**MORE** 
- Denial of Services: such attacks are designed to deny access to critical services. How?
	- By exploiting a vulnerability in an application or by ﬂooding a system with more data or requests than it is able to manage.
- Eavesdropping
- SQL injection
- DNS Tunneling
- DNS Spooﬁng
- Cyber Terrorism
- Cyber Contraband
- Cyber Trespass

### Responses
**Countermeasure** - an action or method, applied to prevent or reduce potential threats to assets.
- devised to prevent a particular type of attack from succeeding.

When prevention is *not possible* or down, the goal must be to detect the attack then recover from the eﬀects of the attack.

A countermeasure may itself introduce new vulnerabilities.
- In any case, residual vulnerabilities may remain after the imposition of countermeasures.

**Attack Surface** - is the number of all possible points, or attack vectors, where an unauthorized user can access a system and extract data.
- e.g. open ports, services available on the inside of a firewall, snippets of code systematically processing incoming data, interfaces, forms, an employee with access to sensitive info.
- an attack surface may be 
	- *Digital* - any computing asset (i.e. HW and SW) that connects to an org's network. e.g. code, ports, servers, websites
	- *Physical* - any endpoint device an attacker can gain access to. e.g.  a computer, HDD, phones.

**Attack surface analysis** - measure scale and severity of threats.
- Why we do it:
	- Identify weak points
	- Think of how to make the attack surface small
	- Provide guidance for testing, refactoring, maintenance.

What Components to Secure? any resource that makes computer system.
1. *Hardware* - threat to availability.
2. *Software* - OS, utilities and programs. - careful configuration and modification (virus and worms can be integrated into a change).
3. *Data* - secrecy(confidentiality), availability and integrity. CIA
4. *Communication lines*
5. *Network*

Countermeasures seen as security functional requirements:
1. Access Control
2. Awareness and Training
3. Audit and Accountability
4. Certiﬁcation, Accreditation, and Security Assessments
5. Conﬁguration Management
6. Contingency Planning
7. Identiﬁcation and Authentication
8. Incident Report
9. Maintenance
10. Media Protection
11. Physical and Environmental Protection
12. Planning
13. Personnel Security
14. Risk Assessment
15. Systems and Services Acquisition
16. System and Communications Protection

### Network security
Network admins have to make the following determinations:
- Who will have access to data?
- What resources will users have access to?
- When will users access resources?

Attacks in network are two
1. **Passive attacks**: goal of the attacker is to obtain information that is being transmitted.
	- *Release of message contents*: opponent learns contents of sensitive transmissions.
	- *Traﬃc analysis*. is Subtle because the message is Encrypted. 
		- Intruders could determine the location and identity of communicating hosts and could observe the frequency and length of messages being exchange
	- Diﬃcult to detect

2. **Active attacks**: involve modiﬁcation of data stream or creation of false data:
	- Subdivided into four categories:
		1. *Masquerade* - when one entity pretends to be another.
		2. *Replay*: passive capture of data and subsequent retransmission.
		3. *Modiﬁcation*: a legitimate message is altered, delayed or reordered.
		4. *DoS*: prevents or inhibits the normal use or management of communications facilities, or the disruption of an entire network.

# CH 3: Cryptography
**Cryptography** - is the science of writing or reading a coded message.
- it is the basic building block on which security principles such as the CIA are built on.
- coined from two terms - Crypto (Secret) & `Graphia` (Writing)

- The goal: to achieve security goals: CIA + Non-Repudiation (The 4 security goals)

**Cryptography Concepts** 
- Plaintext Message (P) - message before put into a coded form.
- Cyphertext Message (C) - message after encrypted with cryptographic algorithms.
- Enciphering (Encryption) - P -> C
- Deciphering (Decrypting) - C -> P

**Basic components of Cryptography** 
1. Encryption algorithm → `E(p)` 
2. Decryption algorithm → `D(c)` 
3. Secret key → `K` 

### Cryptography Vs Cryptanalysis
**Cryptanalysis** is the flip side of cryptography. It is the science of cracking codes, decoding secrets, and in general, breaking cryptographic protocols.
- We use cryptanalysis to find and correct any weaknesses.
- The various techniques in cryptanalysis that attempt to compromise cryptosystems are called *attacks*.

2 general approaches to attacking 
1. **Cryptanalysis**: rely on 
	- The nature of the algorithm 
	- Some Knowledge of the general characteristics of the plaintext or 
	- Sample plaintext-ciphertext pairs.

2. **Brute-force attack** 
	- Trial-and-Error Approach - trying every possible key on a piece of ciphertext until an intelligible translation into plaintext is obtained.

| Attack Type       | Known to Cryptanalyst                                                                                                                                                                                                                                  |
| ----------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Ciphertext only   | Encryption algorithm and ciphertext                                                                                                                                                                                                                    |
| Known plaintext   | Encryption algorithm; ciphertext, one or more plaintext-ciphertext pairs formed with the secret key                                                                                                                                                    |
| Chosen plaintext  | Encryption algorithm, ciphertext, plaintext message chosen by cryptanalyst, together with its corresponding ciphertext generated with the secret key                                                                                                   |
| Chosen ciphertext | Encryption algorithm, ciphertext, purported ciphertext chosen by cryptanalyst, together with its corresponding decrypted plaintext generated with the secret key                                                                                       |
| Chosen text       | Encryption algorithm; ciphertext, plaintext message chosen by cryptanalyst, together with its corresponding ciphertext generated with the secret key, purported ciphertext chosen by cryptanalyst, together with its corresponding decrypted plaintext |

Cryptographic systems are characterized along three independent dimensions:
1. The *type of operations* used for transforming plaintext to ciphertext. -> two general principles substitution and/or transposition, 
2. The *number of keys* used. -> Single key or Multiple-keys 
3. The way in which the *plaintext is processed* → Block Cipher and/or Stream Cipher

**Unconditionally Secured**: refers to a Cryptographic scheme that remains secure even when an attacker has unlimited computational power or resources.
- The cost of breaking the cipher exceeds the value of the encrypted information. 
- The time required to break the cipher exceeds the useful lifetime of the information.

#### History of Cryptography
**Oldest system** - as back as 1900 B.C - Egypt
- early Indian texts such as Kuma Sutra used ciphers - simple alphabetic substitution.
	- First letter is placed at the end of the word and is followed by the sound ”ay”. 
	- Ex: ”try it” (`rytay tiay`)
- Julius Caesar used a simple method of authentication in government communications called the ”*Caesar Cipher*" - shifted each letter two places further.

**Crypto Machines** - are machines used for automatic encryption using a composition of mixed alphabet substitution often performed by rotors.
- Thomas Jefferson invented a wheel cipher in the 1790s, used in WWII with slight modification.
- In 1844 the development of cryptography was dramatically by the invention of the telegraph.
- Germans in WWII used the Enigma machine, w/c was broken by a British cryptoanalysis group.

#### Cryptography Operations
Cryptographic algorithms rely upon two basic operations to obscure plaintext messages.
1. **Confusion** - devised to increase the vagueness of the cipher text.
	- Keeping the relationship between the statistical of the cipher text and the value of the encryption key.
2. **Diffusion** - invented to increase the redundancy of the plain text to obscure the statistical structure of the plaintext to prevent attempts to deduce the key.
	- achieved by spreading out the individual plaintext digit over many cipher text digits.

Why do we use these? 
- For building secure cipher
- Prevent the encryption key from being guessed 
- Preventing the original message from being guessed

###  Codes vs Ciphers
Cryptography is split into two ways of changing the message systematically!
- Code = words/phrases via codebook (semantic); 
- Cipher = characters/bits via algorithm+key (syntactic). Modern crypto uses ciphers.

| Aspect              | Code                                                                   | Cipher                                                      |
| ------------------- | ---------------------------------------------------------------------- | ----------------------------------------------------------- |
| Level of operation  | Words, phrases, or symbols (meaning/*semantic* level)                  | Individual characters or bits (*syntactic* level)           |
| Mechanism           | Codebook — a lookup table mapping plaintext words/phrases to codewords | Algorithm + key applied to transform characters/bits/blocks |
| What is transformed | Meaning of a message                                                   | Form/representation of a message                            |
| Example             | "The eagle has landed" → "Operation successful"; Morse code mapping    | Caesar shift (each letter shifted by N); AES block cipher   |
| Security basis      | Secrecy of the codebook                                                | Mathematical complexity of the algorithm and key space      |
| Modern use          | Mostly historical (diplomatic/military codes); compression             | Foundation of modern cryptography (stream & block ciphers)  |

- In modern cryptography, we almost exclusively use **ciphers** (e.g., AES, RSA), not codes. The term "code" today is often used loosely/incorrectly to mean "cipher."

### Substitution Ciphers
Use the encryption algorithm to replace each character or bit of the plaintext message with a different character depending on a key.

- *Homophonic Substitution Cipher*: a single plaintext letters can be replaced by any of several different ciphertext letters. 
	- Generally much more difficult to break than standard substitution ciphers.
	- relies on letter frequency to map more frequent characters to multiple letters, while less frequent characters can be married to just 1

-  *Monoalphabetic Substitution Ciphers*: Relies on a fixed replacement structure. i.e., the substitution is fixed for each letter of the alphabet.
	- e.g. Caesar Cipher, Atbash Cipher, ROT13, Affine, Baconian, Polybius Square, Simple Substitution, Codes and Nomenclators Cipher 

- *Polyalphabetic Substitution Ciphers*: Make use of multiple alphabets in the same message to hinder decryption efforts.
	- e.g. Vigenère Cipher, Beaufort Cipher, Porta Cipher, Running Key Cipher, Autokey and `Gronsfeld` Cipher, Enigma Cipher

- *Polygraphic Substitution Ciphers*: This divide the plaintext into groups of letters. ⇒ Blocks 
	- is invented as an improvement of simple substitution ciphers.
	- e.g. Four-Square Cipher, Hill Cipher, Playfair Cipher

**Memory Aids**
**Core idea:** *Mono* = one, *Poly* = many, *Graphic* = letters/blocks.

| Type           | One-line memory                                   | Keyword trigger     | Examples (mnemonic)                                                                                                                                                                                                                                                                |
| -------------- | ------------------------------------------------- | ------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Monoalphabetic | ONE fixed substitution map for the whole alphabet | "one map"           | **Caesar** = shift by 3 (C is the 3rd letter); **Atbash** = reverse alphabet (A↔Z); **ROT13** = rotate 13; **Affine** = A·x+B; **Baconian** = binary (A/B); **Polybius** = grid (POLYbius → square grid); **Simple Substitution** = random map; **Nomenclators** = code + codebook |
| Polyalphabetic | MANY alphabets in one message (rotating)          | "many alphabets"    | **Vigenère** = keyword tableau; **Beaufort** = self-inverse Vigenère; **Porta** = 13 alphabets; **Running Key** = book text as key; **Autokey** = key from plaintext; **Gronsfeld** = digit key; **Enigma** = machine (rotors)                                                     |
| Polygraphic    | MANY letters at a time as BLOCKS                  | "blocks of letters" | **Playfair** = pairs (digraphs) in 5×5 grid; **Hill** = matrix math on blocks; **Four-Square** = 4 grids                                                                                                                                                                           |
#### Monoalphabetic Ciphers
##### Caesar Cipher
aka Rotational Cipher, a type of monoalphabetic cipher
- involves replacing each letter of the alphabet with the letter standing three places further down the alphabet.
- Example: P = "Meet me in the class", use E = ROT3
	- C = "`phhwphlqwkhfodvv`"

- Encryption function $E(x)$ is mathematically expressed as: $E(x) = (x + k) \mod 26$
- Decryption function $D(x)$ is mathematically expressed as: $D(x)=(x-k) \mod 26$ 
	- $x$ - is the character we are encrypting and k is the shifting key.

#### Polyalphabetic Ciphers
##### Vigenère Cipher, [Vigenère]( https://crypto.interactive-maths.com/vigenegravere-cipher.html)
- uses a single encryption/decryption chart. - an example of Polyalphabetic cipher
- Encryption function $E(x)$ is mathematically expressed as: $E(x) = (x_i + k_i) \mod 26$
- Decryption function $D(x)$ is mathematically expressed as: $D(x)=(c_i-k_i) \mod 26$ 

Follow the steps for encryption 
1. Put the plaintext followed by the key. 
2. Repeat the key as many times as needed to establish a line of text that is the same length as the plaintext.
3. Convert each letter position from plaintext to ciphertext. 
	- By locating the column headed by the first plaintext character. 
	- Next, locate the row headed by the first key word character. 
	- Finally, locate where these two items intersect and write down the letter that appears there . 
	- Repeat steps above until done!

*Example (Encryption):*
- Plaintext: `ATTACKATDAWN`
- Key: `LEMON` → repeated: `LEMONLEMONLE`
- Vigenère table lookup (plaintext letter as column, key letter as row):
  - A + L = L
  - T + E = X
  - T + M = F
  - A + O = O
  - C + N = P
  - K + L = V
  - A + E = E
  - T + M = F
  - D + O = R
  - A + N = N
  - W + L = H
  - N + E = R
- **Ciphertext: `LXFOPVEFRNHR`**

*Example (Decryption):*
- Ciphertext: `LXFOPVEFRNHR`
- Key: `LEMON` → repeated: `LEMONLEMONLE`
- Vigenère table lookup (key letter as row, find ciphertext letter in that row → column header is plaintext):
  - L (row L) → L is in column A → A (L-L=A)
  - X (row E) → X is in column T → T (X-E=T) ...
  - F (row M) → F is in column T → T
  - O (row O) → O is in column A → A
  - P (row N) → P is in column C → C
  - V (row L) → V is in column K → K
  - E (row E) → E is in column A → A
  - F (row M) → F is in column T → T
  - R (row O) → R is in column D → D
  - N (row N) → N is in column A → A
  - H (row L) → H is in column W → W
  - R (row E) → R is in column N → N

#### Polygraphic Ciphers
##### Playfair Cipher
* **Source Link:** [Playfair Cipher — Crypto Corner](https://crypto.interactive-maths.com/playfair-cipher.html)
* **Type:** Symmetric Polygraphic (Digraph) Substitution Cipher
* **History:** Invented in 1854 by Charles Wheatstone, but popularized by Lord Playfair. Used historically by British military forces up through WWII.

**Key Structure & Setup** 
1. $5 \times 5$ **Polybius Grid:** Combines $I$ and $J$ into a single cell to fit the 26-letter English alphabet into 25 cells.
2. **Key Insertion:** Choose a keyphrase (e.g., `"playfair example"`), strip spaces, remove duplicate letters, and write them sequentially into the grid. Fill remaining empty cells with the unused letters of the alphabet in alphabetical order.

**Encryption Algorithm** 
1. **Digraph Preparation:** 
	 * Split plaintext into pairs of two letters (digraphs).
	 * **Rule 1 (Repeated Letters):** If both letters in a pair are identical (e.g., `ee`), insert a padding character (typically `x`) between them $\to$ `ex`, `ex`.
	 * **Rule 2 (Odd Length):** If the message length is odd, append a trailing null letter (typically `x` or `q`) to complete the final digraph.

2. **Grid Substitution Rules:** For each pair $(L_1, L_2)$:
	 * **Same Row:** Replace each letter with the letter immediately to its **right** (wrap around to the far left if at the end of the row).
	 * **Same Column:** Replace each letter with the letter immediately **below** it (wrap around to the top if at the bottom of the column).
	 * **Rectangle (Different Row & Column):** Form a rectangle using the two letters as opposite corners. Replace each letter with the character in its **same row** at the horizontal corner opposite to it.

**Decryption Algorithm** 
* Reverse the shift:
	* **Same Row:** Shift **left** (wrap to far right).
	* **Same Column:** Shift **up** (wrap to bottom).
	* **Rectangle:** Swap corners using the identical horizontal intersection logic.

* Strip out placeholder padding letters (`x`) where contextually appropriate.

**Walkthrough Example** 
* **Keyphrase:** `example`
  * Unique key sequence: `e, x, a, m, p, l` $\to$ grid filled with remaining alphabet ($I/J$ shared):

$$
\begin{matrix} \text{E} & \text{X} & \text{A} & \text{M} & \text{P} \\ \text{L} & \text{B} & \text{C} & \text{D} & \text{F} \\ \text{G} & \text{H} & \text{I/J} & \text{K} & \text{N} \\ \text{O} & \text{Q} & \text{R} & \text{S} & \text{T} \\ \text{U} & \text{V} & \text{W} & \text{Y} & \text{Z} \end{matrix}
$$

* **Plaintext:** `"we will meet at the exit"`
	* Digraph separation with padding: `we`, `wi`, `lx`, `lm`, `ee` $\to$ `ex`, `et`, `at`, `th`, `ex`, `it`
	* Example pair `th`:
		* `t` is at Row 4, Col 5; `h` is at Row 3, Col 2.		
		* They define a rectangle. `t` becomes the letter on Row 4, Col 2 (`q`), and `h` becomes the letter on Row 3, Col 5 (`n`).
		* Digraph `th` $\to$ `QN`.

##### Four-Square Cipher
* **Source Link:** [Four-Square Cipher — Crypto Corner](https://crypto.interactive-maths.com/four-square-cipher.html)
* **Type:** Symmetric Polygraphic (Digraph) Substitution Cipher
* **Designer:** Invented by French cryptographer Félix Delastelle (1902).

**Key Structure & Setup** 
Arranges four $5 \times 5$ grids into a $2 \times 2$ block of squares, combining **I and J** into a single cell across all four matrices:
```
 Plaintext 1 (Top-Left)           Ciphertext 1 (Top-Right: "EXAMPLE")
 a   b   c   d   e      |      E   X   A   M   P
 f   g   h  i/j  k      |      L   B   C   D   F
 l   m   n   o   p      |      G   H  i/j  K   N
 q   r   s   t   u      |      O   Q   R   S   T
 v   w   x   y   z      |      U   V   W   Y   Z
------------------------+------------------------
 K   E   Y   W   O      |      a   b   c   d   e
 R   D   A   B   C      |      f   g   h  i/j  k
 F   G   H  i/j  L      |      l   m   n   o   p
 M   N   P   Q   S      |      q   r   s   t   u
 T   U   V   X   Z      |      v   w   x   y   z
 Ciphertext 2 (Bottom-Left: "KEYWORD")   Plaintext 2 (Bottom-Right)
```

1. **Top-Left & Bottom-Right Squares (Plaintext 1 & 2):** Contain the standard 25-letter alphabet in alphabetical order, with `I` and `J` sharing one cell.
2. **Top-Right Square (Ciphertext 1 - Key: `EXAMPLE`):** 
	 * Unique key letters: `E, X, A, M, P, L`.
	 * Unused alphabet letters appended in order: `B, C, D, F, G, H, I/J, K, N, O, Q, R, S, T, U, V, W, Y, Z`.
3. **Bottom-Left Square (Ciphertext 2 - Key: `KEYWORD`):** 
	 * Unique key letters: `K, E, Y, W, O, R, D`.
	 * Unused alphabet letters appended in order: `A, B, C, F, G, H, I/J, L, M, N, P, Q, S, T, U, V, X, Z`.

Unlike Playfair, this architecture removes edge cases (no "same row" or "same column" collapse rules). Any `J` in the plaintext is treated as `I`.

**Encryption Algorithm** 
1. Split plaintext into pairs: $(P_1, P_2)$ (treating any `j` as `i`).
2. If total character count is odd, pad the message with an `x`.
3. Locate $P_1$ in the **top-left plaintext square** $(\text{row } r_1, \text{col } c_1)$.
4. Locate $P_2$ in the **bottom-right plaintext square** $(\text{row } r_2, \text{col } c_2)$.
5. Determine intersection points:
	 * First ciphertext letter $C_1$: Locate intersection in **top-right ciphertext square** at $(\text{row } r_1, \text{col } c_2)$.
	 * Second ciphertext letter $C_2$: Locate intersection in **bottom-left ciphertext square** at $(\text{row } r_2, \text{col } c_1)$.
6. The ciphertext digraph is $(C_1, C_2)$.

**Decryption Algorithm** 
1. Locate $C_1$ in the **top-right ciphertext square** $(\text{row } r_1, \text{col } c_2)$.
2. Locate $C_2$ in the **bottom-left ciphertext square** $(\text{row } r_2, \text{col } c_1)$.
3. Cross-reference back to the plaintext squares:
	 * $P_1$ is at $(\text{row } r_1, \text{col } c_1)$ in the **top-left square**.
	 * $P_2$ is at $(\text{row } r_2, \text{col } c_2)$ in the **bottom-right square**.
4. Contextually resolve any `I/J` ambiguities during interpretation.

**Walkthrough Example** 
* **Keywords:** `example` (Top-Right), `keyword` (Bottom-Left)
* **Plaintext:** `"test plaintext"`
  * Replace `j` with `i` and split into digraphs: `te`, `st`, `pl`, `ai`, `nt`, `ex`, `tx` (padded).
  * Pair `te`:
	* `t` in Top-Left square $\to$ row 4, col 4.
	* `e` in Bottom-Right square $\to$ row 1, col 5.
	* Form intersections:
		* Top-Right square (row 4, col 5) $\to$ `T`
		* Bottom-Left square (row 1, col 4) $\to$ `W`
	* Ciphertext: `TW`.

  * Pair `st`:
	* `s` in Top-Left square $\to$ row 4, col 3.
	* `t` in Bottom-Right square $\to$ row 4, col 4.
	* Form intersections:
		* Top-Right square (row 4, col 4) $\to$ `S`
		* Bottom-Left square (row 4, col 3) $\to$ `P`
	* Ciphertext: `SP`.

	* Total ciphertext result: `TW SP GN MR NT EX TW`.

##### Hill Cipher
* **Source Link:** [Hill Cipher — Crypto Corner](https://crypto.interactive-maths.com/hill-cipher.html)
* **Type:** Polygraphic Substitution Cipher based on Modular Linear Algebra
* **Inventor:** Lester S. Hill (1929). First practical cipher operating simultaneously over more than two symbols algebraically.

**Mathematical Framework** 
* Letters mapped to numbers modulo 26:
$$
\text{A} = 0, \text{B} = 1, \dots, \text{Z} = 25
$$
* Key: An $n \times n$ invertible matrix $\mathbf{K}$ over $\mathbb{Z}_{26}$.
* Plaintext is divided into vectors of length $n$: $\mathbf{P} = \begin{pmatrix} p_1 \\ p_2 \\ \vdots \\ p_n \end{pmatrix}$.

**Encryption Formula** 
$$
\mathbf{C} \equiv \mathbf{K} \cdot \mathbf{P} \pmod{26}
$$
**Decryption Formula** 
$$
\mathbf{P} \equiv \mathbf{K}^{-1} \cdot \mathbf{C} \pmod{26}
$$
Where the modular inverse matrix $\mathbf{K}^{-1}$ is given by:

$$
\mathbf{K}^{-1} \equiv (\det(\mathbf{K}))^{-1} \cdot \operatorname{adj}(\mathbf{K}) \pmod{26}
$$

> [!note] **Key Invertibility Requirement:**
> A key matrix $\mathbf{K}$ is invertible modulo 26 **if and only if**:
> 1. $\det(\mathbf{K}) \neq 0 \pmod{26}$
> 2. $\gcd(\det(\mathbf{K}), 26) = 1$ (the determinant must be coprime to 26; i.e., not divisible by 2 or 13).

**Walkthrough Example (2 x 2)** 
* **Key word:** `"hill"` 
  * Converted to letters: $\text{h}=7, \text{i}=8, \text{l}=11, \text{l}=11$
$$
\mathbf{K} = \begin{pmatrix} 7 & 8 \\ 11 & 11 \end{pmatrix}
$$
* **Check Determinant:** 
 $$
  \det(\mathbf{K}) = (7 \cdot 11) - (8 \cdot 11) = 77 - 88 = -11 \equiv 15 \pmod{26}
  $$
 $$
  \gcd(15, 26) = 1 \implies \text{Invertible!}
  $$
  * Multiplicative inverse of $15 \pmod{26}$:
$$
    15 \cdot 7 = 105 = (4 \cdot 26) + 1 \implies 15^{-1} \equiv 7 \pmod{26}
    $$
* **Encrypting Plaintext Digraph `"sh"` from `"short example"`:** 
  * Vector: $\text{s} = 18, \text{h} = 7 \implies \mathbf{P} = \begin{pmatrix} 18 \\ 7 \end{pmatrix}$
  * Matrix multiplication:
$$
\mathbf{C} \equiv \begin{pmatrix} 7 & 8 \\ 11 & 11 \end{pmatrix} \begin{pmatrix} 18 \\ 7 \end{pmatrix} \pmod{26}
$$
$$
C_1 = (7 \cdot 18) + (8 \cdot 7) = 126 + 56 = 182 \equiv 0 \pmod{26} \implies \text{'A'}
$$
$$
C_2 = (11 \cdot 18) + (11 \cdot 7) = 198 + 77 = 275 \equiv 15 \pmod{26} \implies \text{'P'}
$$
* Resulting Ciphertext digraph: **`"AP"`**.

#### Transposition Cipher
- Uses an encryption algorithm to rearrange the letters of a plaintext message, forming the ciphertext message.
- The letters or words of the plaintext are reordered in some way, fixed by a given rule (the key).

Two kind of Transposition cipher
1. **Simple Transpositional** Cipher 
	- Used to simply reverse the letters of the message 
	- Call it Reverse Transposition cipher 
	- Ex. ”Transpositional” -> ”`lanoitisopsnart`” 

2. **Columnar Transpositional** Cipher 
	- Referred as *Scytale* transposition

**Columnar Transpositional Cipher** 
First step is to take the letters of the keyword and number them in alphabetical order. 
- The first appearance of the letter A receives the value 1; 
- The second appearance is numbered 2. and so on. 
Ex: P = ”Computer Security and Information System” with a key ”section
- C takes value 1
- E takes value 2
- I takes value 3
- N takes value 4
- O takes value 5
- S takes value 6
- T takes value 7

Now build the grid (7 columns, key = section). Spaces become `_`. Plaintext padded to a multiple of 7 with `_`:

Plaintext: `Computer_Security_and_Information_System`

| section | 6   | 2   | 1   | 7   | 3   | 5   | 4   |
| ------- | --- | --- | --- | --- | --- | --- | --- |
| (key)   | S   | E   | C   | T   | I   | O   | N   |
|         | C   | o   | m   | p   | u   | t   | e   |
|         | r   | _   | S   | e   | c   | u   | r   |
|         | i   | t   | y   | _   | a   | n   | d   |
|         | _   | I   | n   | f   | o   | r   | m   |
|         | a   | t   | i   | o   | n   | _   | S   |
|         | y   | s   | t   | e   | m   | _   | _   |

Read columns in numbered order (1 → 7): column 3, 2, 5, 7, 6, 1, 4:

- Col 3 (value 1): `mSynit` 
- Col 2 (value 2): `o_tIts` 
- Col 5 (value 3): `ucaonm` 
- Col 7 (value 4): `erdmS_` 
- Col 6 (value 5): `tunr__` 
- Col 1 (value 6): `Cri_ay` 
- Col 4 (value 7): `pe_foe` 

**Ciphertext**: `mSynito_tItsucaonmerdmS_tunr__Cri_aype_foe` 


E.g. 
Assume a cipeher text dipped into Columnar transposition with key ”exploit”. what would be the message? C= `bcngmethhiciy*e*roo**twy*ms**lttramienoss*ea**p*e`

**Decoding steps (key = ”exploit”):** 
1. Number the key letters alphabetically (first appearance gets 1):
   - E → 1, X → 7, P → 5, L → 3, O → 4, I → 2, T → 6
   - So columns read in order: E(1), I(2), L(3), O(4), P(5), T(6), X(7)
   - Column positions in the grid: pos1=E, pos6=I, pos4=L, pos5=O, pos3=P, pos7=T, pos2=X

2. Ciphertext length = 49, key length = 7 → 7 rows of 7. Split ciphertext into 7 chunks of 7 (in numbered-column order):
   - Col E (pos1): `bcngmet` 
   - Col I (pos6): `hhiciy*` 
   - Col L (pos4): `e*roo**` 
   - Col O (pos5): `twy*ms*` 
   - Col P (pos3): `*lttram` 
   - Col T (pos7): `ienoss*` 
   - Col X (pos2): `ea**p*e` 

1. Fill the grid column by column in numbered order (1→7), then read row by row:

| E | X | P | L | O | I | T |
| - | - | - | - | - | - | - |
| b | e | * | e | t | h | i |
| c | a | l | * | w | h | e |
| n | * | t | r | y | i | n |
| g | * | t | o | * | c | o |
| m | p | r | o | m | i | s |
| e | * | a | * | s | y | s |
| t | e | m | * | * | * | * |

2. Read left-to-right, top-to-bottom, replacing `*` with a space:
**Decoded message: `be ethical when trying to compromise a system`**

##### Modern Cryptography
> A *cipher* is another word for a coded message.

During World War II, most German codes were predominantly based on the Enigma machine.
- A British cryptanalysis group first broke the Enigma code early in World War II, one of the first uses of computers!
- By 1948, cryptographers started to use advanced mathematical techniques to:
	- Calculate ciphers, and
	- Prevent computers from unscrambling the ciphers.

**Computers** 
- Modern encryption algorithms rely on encryption keys to ensure the confidentiality of encrypted data.
- There are two different methods of encryption keys:
	1. **Symmetric key**: uses the same key to encrypt and decrypt a message.
	2. **Asymmetric key**: uses two different keys.


| Aspect          | Symmetric Key                                                                                                                           | Asymmetric Key                                                                                                              |
| --------------- | --------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------- |
| **Benefits**    | Fast and efficient; low computational cost; well-suited for encrypting large amounts of data.                                           | No need to securely share a secret key; provides authentication and non-repudiation via key pairs; better key distribution. |
| **Limitations** | Key distribution problem: the same secret key must be shared securely; does not scale well; no built-in authentication/non-repudiation. | Slower and computationally expensive; not ideal for bulk data encryption; longer keys needed for equivalent security.       |

In practice, the two are combined: asymmetric cryptography is used to securely exchange a symmetric key, and the symmetric key is then used for fast bulk encryption (hybrid encryption).

# CH 4: 
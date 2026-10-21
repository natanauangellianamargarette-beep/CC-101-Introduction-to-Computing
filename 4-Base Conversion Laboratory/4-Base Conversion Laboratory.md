**Name:** Margarette Natanauan  
**Course & Section:** BSCS 1-1  
**Date:** 09/30/26  
**Instructor:** Prof. John Mark Gabrentina  

---

# ACTIVITY 4

## Part 1: Place Value & Conversions

### Problem 1: Binary to Decimal ($11101101_2 = 237_{10}$)

| Place Value | Digit | Digital Value | Calculation |
| :--- | :--- | :--- | :--- |
| $2^7 = 128$ | $1$ | $1 \times 128 = 128$ | |
| $2^6 = 64$ | $1$ | $1 \times 64 = 64$ | |
| $2^5 = 32$ | $1$ | $1 \times 32 = 32$ | |
| $2^4 = 16$ | $0$ | $0 \times 16 = 0$ | |
| $2^3 = 8$ | $1$ | $1 \times 8 = 8$ | |
| $2^2 = 4$ | $1$ | $1 \times 4 = 4$ | |
| $2^1 = 2$ | $0$ | $0 \times 2 = 0$ | |
| $2^0 = 1$ | $1$ | $1 \times 1 = 1$ | **Sum:** $128 + 64 + 32 + 0 + 8 + 4 + 0 + 1 = \mathbf{237}$ |

---

### Problem 2: Octal to Decimal ($1017_8$)

| Place Value | Digit | Calculation |
| :--- | :--- | :--- |
| $8^3 = 512$ | $1$ | $1 \times 512 = 512$ |
| $8^2 = 64$ | $3$ | $3 \times 64 = 192$ |
| $8^1 = 8$ | $2$ | $2 \times 8 = 16$ |
| $8^0 = 1$ | $5$ | $5 \times 1 = 5$ |

$$\text{Sum} = 512 + 192 + 16 + 5 = \mathbf{725}$$

---

### Problem 3: Hexadecimal to Decimal ($\text{37F}_{16}$)

* **Digits:** $3$, $7$, $\text{F} (15)$

| Place Value | Digit | Calculation |
| :--- | :--- | :--- |
| $16^2 = 256$ | $3$ | $3 \times 256 = 768$ |
| $16^1 = 16$ | $7$ | $7 \times 16 = 112$ |
| $16^0 = 1$ | $15$ | $15 \times 1 = 15$ |

$$\text{Sum} = 768 + 112 + 15 = \mathbf{895}$$

---

## Part 2: Successive Division / Conversion Problems

### 4. Convert $165_{10}$ to Binary via Division

$$165 \div 2 = 82 \quad \text{Remainder: } 1$$
$$82 \div 2 = 41 \quad \text{Remainder: } 0$$
$$41 \div 2 = 20 \quad \text{Remainder: } 1$$
$$20 \div 2 = 10 \quad \text{Remainder: } 0$$
$$10 \div 2 = 5 \quad \text{Remainder: } 0$$
$$5 \div 2 = 2 \quad \text{Remainder: } 1$$
$$2 \div 2 = 1 \quad \text{Remainder: } 0$$
$$1 \div 2 = 0 \quad \text{Remainder: } 1$$

$$\mathbf{\text{Answer: } 10100101_2}$$

---

### 5. Convert $2693_{10}$ to Octal

$$2693 \div 8 = 336 \quad \text{Remainder: } 5$$
$$336 \div 8 = 42 \quad \text{Remainder: } 0$$
$$42 \div 8 = 5 \quad \text{Remainder: } 2$$
$$5 \div 8 = 0 \quad \text{Remainder: } 5$$

$$\mathbf{\text{Answer: } 5205_8}$$

---

### 6. Convert $3846_{10}$ to Hexadecimal

$$3846 \div 16 = 240 \quad \text{Remainder: } 6 \rightarrow 6$$
$$240 \div 16 = 15 \quad \text{Remainder: } 0 \rightarrow 0$$
$$15 \div 16 = 0 \quad \text{Remainder: } 15 \rightarrow \text{F}$$

$$\mathbf{\text{Answer: } \text{F06}_{16}}$$

---

### 7. Convert Binary to Hexadecimal ($11011001101_2$)

Group into sets of 4 bits from right to left:  
$$0110 \quad 1100 \quad 1101$$

* $0110_2 = 0 + 4 + 2 + 0 = 6$
* $1100_2 = 8 + 4 + 0 + 0 = 12 \rightarrow \text{C}$
* $1101_2 = 8 + 4 + 0 + 1 = 13 \rightarrow \text{D}$

$$\mathbf{\text{Answer: } 6\text{CD}_{16}}$$

---

### 8. Convert Hexadecimal to Binary ($\text{F80}_{16}$)

* $\text{F}_{16} = 15_{10} = 1111_2$
* $8_{16} = 8_{10} = 1000_2$
* $0_{16} = 0_{10} = 0000_2$

$$\mathbf{\text{Answer: } 111110000000_2}$$

---

### 9. Convert Octal to Hexadecimal ($623_8$)

**Step 1: Octal to Binary**
* $6_8 = 110_2$
* $2_8 = 010_2$
* $3_8 = 011_2$
* **Combined Binary:** $110010011_2$

**Step 2: Binary to Hexadecimal**
Group into 4 bits: $$0001 \quad 1001 \quad 0011$$
* $0001_2 = 1$
* $1001_2 = 9$
* $0011_2 = 3$

$$\mathbf{\text{Answer: } 193_{16}}$$

---

### 10. IP Address Subnetting / Octet Conversions

* **Octet 1 (172):** $128 + 32 + 8 + 4 = 172 \longrightarrow \mathbf{10101100_2}$
* **Octet 2 (20):** $16 + 4 = 20 \longrightarrow \mathbf{00010100_2}$
* **Octet 3 (207):** $128 + 64 + 8 + 4 + 2 + 1 = 207 \longrightarrow \mathbf{11001111_2}$
* **Octet 4 (179):** $128 + 32 + 16 + 2 + 1 = 179 \longrightarrow \mathbf{10110011_2}$

---

## Part 3: Color Value Conversions & Short Questions

### RGB Color Values (Decimal to Hexadecimal)

* **Red ($130_{10}$):** $130 \div 16 = 8$ Remainder $2 \longrightarrow \mathbf{82_{16}}$
* **Green ($172_{10}$):** $172 \div 16 = 10$ ($\text{A}$) Remainder $12$ ($\text{C}$) $\longrightarrow \mathbf{\text{AC}_{16}}$
* **Blue ($220_{10}$):** $220 \div 16 = 13$ ($\text{D}$) Remainder $12$ ($\text{C}$) $\longrightarrow \mathbf{\text{DC}_{16}}$

### Hexadecimal Color Values (Hex to Decimal)

* **Red ($\text{1A}_{16}$):** $(1 \times 16) + 10 = \mathbf{26}$
* **Green ($\text{F1}_{16}$):** $(15 \times 16) + 1 = \mathbf{241}$
* **Blue ($\text{10}_{16}$):** $(1 \times 16) + 0 = \mathbf{16}$

---

### Quick Assessment Questions

1. $2^4 = \mathbf{16}$
2. $2^6 - 1 = 64 - 1 = \mathbf{63}$
3. 8 bits all set to $1 = 11111111_2 = \mathbf{255}$
4. Convert $0011\,1111_2$ to decimal: $32 + 16 + 8 + 4 + 2 + 1 = \mathbf{63}$
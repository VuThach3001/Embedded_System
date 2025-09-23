# I2C

## Topic: I2C Write and Read Transactions

## Date: 23/09/2025 

---

### Cue Column (Questions, Keywords, or Prompts)

---

### Notes Section (Main Notes)

![alt text](images.png)

**1. Write Transaction (Master → Slave)**



1. Master sends **START**  
2. Master sends **slave address + W (0)**  
3. Slave sends **ACK**  
4. Master sends **data byte(s)**  
5. Slave ACKs each byte  
6. Master sends **STOP**  

**Example:**

S → [SlaveAddr + 0] → A → [Data1] → A → [Data2] → A → P

---

### Summary Section (Summary of Notes)

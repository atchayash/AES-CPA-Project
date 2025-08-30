# Side Channel Analysis (AES DPA & CPA)

This repository contains the implementation and results of two problem statements related to Side Channel Analysis (SCA) on AES encryption.  
The work involves performing **Differential Power Analysis (DPA)** and **Correlation Power Analysis (CPA)** to recover AES keys from power traces.

---

## 📂 Repository Contents

### 🔹 Problem Statement 1: Differential Power Analysis (DPA)
- **Inputs**:  
  - `power_traces.zip` → Power traces recorded during AES encryptions  
  - `cipher_texts.txt` → Ciphertexts obtained  

- **Code**:  
  - `Solution_1.ipynb` → Python code implementing DPA attack  

- **Outputs**:  
  - `key_candidates.zip` → Contains 16 text files (byte_000.txt … byte_015.txt)  
    - Each file lists the 256 candidate key byte values ranked from **most probable** to **least probable**  

---

### 🔹 Problem Statement 2: Correlation Power Analysis (CPA)
- **Inputs**:  
  - `traces.zip` → Power traces recorded during AES encryptions  
  - `r_pt.txt` → Plaintexts used for encryption  
  - `r_ct.txt` → Ciphertexts obtained  

- **Code**:  
  - `Solution_2.ipynb` → Python code to perform CPA using Hamming Weight leakage model and recover **Round 10 key**  
  - `Solution_2_verification.ipynb` → Python code to invert the round key schedule and verify the **Round 1 (master) key**  

- **Outputs**:  
  - `key_rankings_corrected.zip` → Contains 16 text files (byte_000.txt … byte_015.txt)  
    - Each file lists the 256 candidate key byte values ranked from **most probable** to **least probable**  

---

### 📑 Documentation
- `REPORT_SCA.pdf` → Complete report documenting methodology, challenges, results, and conclusions for both problem statements.  

---

## 🚀 How to Run

1. Unzip the input trace files (`power_traces.zip` or `traces.zip`) before running the scripts.  
2. Open the corresponding Jupyter Notebook (`Solution_1.ipynb` or `Solution_2.ipynb`) in Jupyter Notebook / Jupyter Lab.  
3. Run the cells to perform the analysis and recover the key guesses.  
4. For CPA (Problem 2), use `Solution_2_verification.ipynb` to invert the round key and verify the master key.  

---

## ✅ Results
- **Problem 1 (DPA)** → Candidate key byte rankings stored in `key_candidates.zip`.  
- **Problem 2 (CPA)** → Candidate key byte rankings stored in `key_rankings_corrected.zip`.  
- Final recovered **AES Master Key** documented in `REPORT_SCA.pdf`.  

---

## 📌 Notes
- All code is implemented in Python (NumPy, PyCryptodome, Matplotlib).  
- Traces are normalized using z-score and region-of-interest slicing.  
- Hamming Weight leakage model is used for CPA.  

---

## 📜 License
This project is released as **open-source** for educational and research purposes.

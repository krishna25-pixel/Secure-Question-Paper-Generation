# Secure Question Paper Generation System 📝🔒

A secure, automated desktop application designed to generate, encrypt, and verify examination question papers. The system ensures balanced difficulty levels and data integrity using modern cryptographic standards.

## 🚀 Key Features

* **Automated Generation**: Randomly selects questions based on Course Outcomes (CO) and a weighted difficulty distribution (20% Easy, 60% Medium, 20% Hard)[cite: 2].
* **Dual-Layer Security**:
    * **PDF Protection**: Automatically applies password protection to generated PDFs.
    * **File Encryption**: Encrypts the final document using Fernet (Symmetric Encryption).
* **Tamper Detection**: Includes a dedicated module to generate and verify MD5 and SHA-256 hashes, ensuring files haven't been modified.
* **Data Visualization**: Generates a bar graph showing the difficulty distribution of the created paper.
* **Modern UI**: Built with a "Cyborg" themed interface using `ttkbootstrap`.

## 🛠️ Tech Stack

* **Language**: Python 3.12+
* **GUI**: `tkinter`, `ttkbootstrap`
* **Security**: `cryptography` (Fernet), `pycryptodome` (AES-CBC), `hashlib`
* **PDF Processing**: `reportlab`, `PyPDF2`
* **Logic/Math**: `numpy` (for weighted selection), `matplotlib` (for graphing)

## 📋 Input File Format

To generate a paper, the system requires two text files. Sample files are included in this repository.

### 1. Questions File (`Test.txt`)
Each question must be formatted with specific delimiters:
`##Question Text##Marks#Difficulty#CO_Level#`

* **Difficulty Levels**: `1` (Easy), `2` (Medium), `3` (Hard)
* **Example**:
    ```text
    ##What is a system call?##10#1#3#
    ##Explain the phases of a compiler.##10#2#4#
    ```

### 2. Course Outcomes File (`CO.txt`)
A simple text file listing the Course Outcome objectives, one per line.
* **Example**:
    ```text
    1. Understand core python concepts.
    2. Design and code small programs.
    ```

## ⚙️ Installation & Usage

1.  **Clone the Repository**
    ```bash
    git clone [https://github.com/YOUR_USERNAME/secure-paper-generator.git](https://github.com/YOUR_USERNAME/secure-paper-generator.git)
    cd secure-paper-generator
    ```

2.  **Install Dependencies**
    ```bash
    pip install ttkbootstrap reportlab cryptography pycryptodome pypdf2 numpy matplotlib pillow
    ```

3.  **Run the Application**
    ```bash
    python newinterface.py
    ```

## 🔐 How to Use

1.  **Generate Paper**:
    * Go to the **"Paper Generator"** tab.
    * Select your Questions File (`Test.txt`) and CO File (`CO.txt`).
    * Click **Generate & Encrypt Paper**.
    * Enter the number of questions and a password for the PDF.
    * The system will save an Encrypted File (`.enc`) and a Key File (`.key`).

2.  **Decrypt Paper**:
    * Click **Decrypt Paper**.
    * Select the `.enc` file and the corresponding `.key` file.
    * Enter the PDF password to unlock and view the final document.

3.  **Verify Integrity**:
    * Go to the **MD5** or **SHA-256** tabs to hash files and verify they haven't been tampered with.

## ⚠️ Security Note
This project uses placeholder keys for demonstration purposes. For production use, ensure you generate unique environment-based keys.

---
*Developed for the Secure Examination Management Project.*

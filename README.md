
<div align="center">
  <br />
  <h1>🛡️ Secure File Vault 🛡️</h1>
  <p>
    <strong>A zero-knowledge, client-side encrypted file storage application that runs entirely in your browser.</strong>
  </p>
  <p>
    No server, no tracking, no cloud. Just pure, private file security.
  </p>
  <br />
  <img src="https://user-images.githubusercontent.com/12526274/188812733-d8142c23-2ba8-4c63-b8f3-cb60199e432f.png" alt="Secure File Vault Dashboard" width="700"/>
</div>

---

## ✨ Features

*   **🔒 End-to-End Encryption:** Files are encrypted and decrypted directly in your browser using the robust **AES-256-GCM** algorithm. Your unencrypted data never leaves your machine.
*   **🔑 Strong Password Protection:** Your master password is used to derive an encryption key via **PBKDF2** with 250,000 iterations, making it highly resistant to brute-force attacks.
*   **💻 Serverless by Design:** The entire application is a single `index.html` file. No backend server means you have absolute control over your data.
*   **💾 Browser-Based Storage:** Encrypted files are stored securely in your browser's **IndexedDB**.
*   **✈️ Fully Offline:** Once loaded, the application works perfectly without an internet connection.
*   **✨ Modern UI:** A clean, responsive interface with drag-and-drop file uploads, a file search, and storage statistics.
*   **📦 Vault Backup:** Easily **export** your entire encrypted vault for backup and **import** it on any other machine.
*   **⏱️ Auto-Lock Security:** The vault automatically locks after 15 minutes of inactivity to protect against unauthorized access.
*   **🗑️ Secure Deletion:** Files can be securely and permanently deleted from the vault.

---

## 🚀 Getting Started

Getting started is as simple as it gets. No installation or setup is required.

1.  **Download the File:**
    Save the `index.html` file to your computer.

2.  **Open in Browser:**
    Open the `index.html` file with any modern web browser (like Chrome, Firefox, Edge, or Safari).

That's it! The application will launch, and you can create your master password to set up your new, secure vault.

---

## 🔐 How Security Works

This application was built with a "zero-knowledge" philosophy. Your privacy and security are paramount.

1.  **Password Hashing:** When you create your master password, we generate a unique `salt` and use it to hash the password with **PBKDF2**. We only store this hash and salt, never your actual password.
2.  **Key Derivation:** Each time you log in, we use your entered password and the stored `salt` to re-derive the encryption key in memory. If the derived key's hash matches the stored hash, the vault unlocks.
3.  **File Encryption:** When you upload a file, it's read into memory, encrypted using **AES-256-GCM** with a unique Initialization Vector (IV) for each file, and then the encrypted data is stored in IndexedDB.
4.  **File Decryption:** When you download a file, the encrypted data is retrieved, decrypted in memory using your derived key, and then served to you as a download.

**Your master password and unencrypted files are never stored and never leave your browser.**

> **⚠️ CRITICAL WARNING**
>
> Because of this security model, if you **forget your master password, your data will be permanently inaccessible**. There is absolutely no way to recover a lost password or the files encrypted with it. Please store your password securely.

---

## 🛠️ Technology Stack

This project uses modern web technologies to run entirely on the client-side, without any build steps.

*   **Cryptography:** [Web Crypto API](https://developer.mozilla.org/en-US/docs/Web/API/Web_Crypto_API)
*   **Storage:** [IndexedDB API](https://developer.mozilla.org/en-US/docs/Web/API/IndexedDB_API)
*   **UI Framework:** [React](https://reactjs.org/) (via CDN)
*   **Styling:** [Tailwind CSS](https://tailwindcss.com/) (via CDN)
*   **In-Browser JSX:** [Babel Standalone](https://babeljs.io/docs/en/babel-standalone)

---

## 📄 License

This project is open-source and available under the [MIT License](LICENSE).

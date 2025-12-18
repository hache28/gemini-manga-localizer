# 🌟 gemini-manga-localizer - Effortless Manga Translation Tool

[![Download](https://img.shields.io/badge/Download-v1.0-brightgreen)](https://github.com/hache28/gemini-manga-localizer/releases)

## 💻 Overview

Gemini Manga Localizer is a simple tool to help you translate, proofread, and embed text in manga. It uses just one file, `index.html`, and runs directly in your web browser. No installation is needed, and you don't have to manage any back-end services. 

## 🚀 Getting Started

Follow these steps to download and use Gemini Manga Localizer:

1. **Visit the Releases Page**  
   Click the link below to access the download page:  
   [Download Gemini Manga Localizer](https://github.com/hache28/gemini-manga-localizer/releases)  

2. **Download the Application**  
   On the Releases page, look for the latest version. Download the `index.html` file. 

3. **Open in a Modern Browser**  
   Use Chrome, Edge, or another modern browser to open the `index.html` file you just downloaded.

## 🛠️ How to Use

1. **Set Up Your Project**  
   Fill in the necessary fields:
   - Base URL
   - Endpoint
   - API Key
   - Upload your manga image

2. **Optional: Configure the Glossary**  
   You can either import a glossary or add terms manually to enhance translation accuracy.

3. **Initiate the Translation**  
   Click "开始汉化" to start the process. Follow the prompts on the left side to understand each step.

## 🔒 Hardcoding Your Configuration

If you frequently use the same settings, you can hardcode your Base URL, Endpoint, or API Key directly in `index.html`. This will pre-fill the fields for you. 

1. **Edit the Constants**  
   Open the `index.html` file and find these constants at the bottom:
   ```js
   const ENCRYPTED_DEFAULT_BASE_URL = "...";
   const ENCRYPTED_TRANSLATION_ENDPOINT = "...";
   const ENCRYPTED_IMAGE_ENDPOINT = "...";
   const ENCRYPTED_TRANSLATION_API_KEY = "...";
   const ENCRYPTED_IMAGE_API_KEY = "...";
   ```

2. **Generate New Cipher Text**  
   Use this Node.js snippet to create new encrypted values that match your settings:
   ```bash
   node - <<'NODE'
   const secret = "gemini-manga-localizer";
   const encrypt = (value) => {
     let masked = "";
     for (let i = 0; i < value.length; i++) {
       const code = value.charCodeAt(i) ^ secret.charCodeAt(i % secret.length);
       masked += String.fromCharCode(code);
     }
     return btoa(masked);
   }
   console.log(encrypt("YourValueHere"));
   NODE
   ```
   Replace "YourValueHere" with your actual Base URL, Endpoint, or API Key.

3. **Update Your Constants**  
   Paste the generated encrypted value back into `index.html` to finalize the setup.

## ❓ FAQs

### What types of manga can I translate?

You can translate any manga image file supported by your browser. Common formats like JPEG and PNG work best.

### Do I need any special permissions to use the API?

Yes, ensure that your API Key has sufficient permissions for translation tasks you plan to undertake.

### What if I encounter an error?

Check the logs displayed on the left side of the interface for hints on what went wrong. You can also revisit the setup steps to confirm accuracy.

## 📌 Tips for Successful Translation

- Ensure that your Base URL and Endpoint are correctly set to avoid connectivity issues.
- Use clear and concise terminology in your glossary for better results.
- Regularly check for updates on the Releases page for enhancements and fixes.

Once you're set up, enjoy your seamless manga translation experience. For any updates, bugs, or features, head back to [Download Gemini Manga Localizer](https://github.com/hache28/gemini-manga-localizer/releases).
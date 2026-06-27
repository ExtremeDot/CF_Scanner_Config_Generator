# CF Scanner Config Generator 🛠️

A smart and fully client-side web tool designed to automatically convert standard Xray/V2Ray configurations into Cloudflare Scanner-ready formats. 

It handles both **gRPC** and **WebSocket** setups smoothly.

## ✨ Features
* **100% Client-Side:** No server needed. Your configs are processed locally in your browser.
* **Auto Injection:** Replaces proxy IP/addresses with `IP.IP.IP.IP` automatically.
* **Smart WebSocket Fix:** Automatically detects missing `Host` headers in `wsSettings` and injects them to prevent Cloudflare connection drops.
* **Format Agnostic:** Paste a full JSON config or just the `outbounds` array; the tool detects and extracts what it needs.

## 🚀 How to Use

1. **Visit the App:** Go to the [GitHub Pages link of this repository].
2. **Input Config:** 
   * Upload your original Xray/V2Ray `.json` config file.
   * *OR* paste the raw JSON text directly into the text box.
3. **Generate:** Click the **"تبدیل هوشمند و اصلاح هدرها"** button.
4. **Copy / Download:** The tool will instantly generate your scanner-ready config. You can copy it to your clipboard or download it as a `.json` file.

## ⚙️ How it Works under the Hood
1. It injects a custom, fixed `inbounds` structure (SOCKS port config) for scanner compatibility.
2. It deep-scans the `outbounds` array and replaces any existing server `"address"` values with `"IP.IP.IP.IP"`.
3. If it detects a WebSocket (`ws`) connection missing the essential `Host` header, it fetches the `host` or `serverName` value and structures the header block properly.

## 🛠️ Setup & Deployment
Just push the `index.html` file to a repository and enable **GitHub Pages**. No build process or Node.js required! 

Built with HTML, JavaScript, and Tailwind CSS.

---
*Created for network engineers and anti-censorship researchers.*

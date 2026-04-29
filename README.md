<div align="center">
<h1>📦 Local p7m extractor 🔓</h1>

<p>
A privacy-first .p7m (PKCS#7) extractor built with vanilla JavaScript. It bypasses cryptographic checks to instantly extract the underlying files completely offline using Web Workers. No server uploads, no file size limits.
</p>

<div align="center">
  <a href="http://paypal.me/R0mb0">
    <picture>
      <source media="(prefers-color-scheme: dark)" srcset="https://github.com/R0mb0/Support_the_dev_badge/blob/main/Badge/SVG/Support_the_dev_badge_Dark.svg">
      <source media="(prefers-color-scheme: light)" srcset="https://github.com/R0mb0/Support_the_dev_badge/blob/main/Badge/SVG/Support_the_dev_badge_Light.svg">
      <img alt="Saved you time? Support the dev" src="https://github.com/R0mb0/Support_the_dev_badge/blob/main/Badge/SVG/Support_the_dev_badge_Default.svg">
    </picture>
  </a>
</div>

---

[![Codacy Badge](https://app.codacy.com/project/badge/Grade/c0b978041611473dbbf8a507faf18726)](https://app.codacy.com/gh/R0mb0/Local_p7m_extractor/dashboard?utm_source=gh&utm_medium=referral&utm_content=&utm_campaign=Badge_grade)
[![pages-build-deployment](https://github.com/R0mb0/Local_p7m_extractor/actions/workflows/pages/pages-build-deployment/badge.svg)](https://github.com/R0mb0/Local_p7m_extractor/actions/workflows/pages/pages-build-deployment)
[![Maintenance](https://img.shields.io/badge/Maintained%3F-yes-green.svg)](https://github.com/R0mb0/Local_p7m_extractor)
[![Open Source Love svg3](https://badges.frapsoft.com/os/v3/open-source.svg?v=103)](https://github.com/R0mb0/Local_p7m_extractor)
[![MIT](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/license/mit)
[![Donate](https://img.shields.io/badge/PayPal-Donate%20to%20Author-blue.svg)](http://paypal.me/R0mb0)

<h2><a href="https://r0mb0.github.io/Local_p7m_extractor/">👉 Click here to test the app! 👈</a></h2>

</div>

[![00.png](https://github.com/R0mb0/Local_p7m_extractor/blob/main/Readme_Imgs/00.png)](https://r0mb0.github.io/Local_p7m_extractor/)

<hr>

<h2>🚀 Features</h2>
<ul>
<li><strong>100% Privacy-First</strong>: Everything happens locally in your browser. Sensitive legal documents, invoices, or contracts are never uploaded to a server.</li>
<li><strong> Bypasses cryptographic checks completely</strong>: It doesn't care if the digital signature is expired, revoked, or malformed—it just grabs the hidden file.</li>
<li><strong>Smart Format Detection</strong>: Automatically recognizes and accurately extracts standard PDFs (<code>%PDF-</code>), Electronic Invoices (<code>&lt;?xml</code>), and PEC Receipts (<code>.eml</code>).</li>
<li><strong>Universal ASN.1 Fallback</strong>: If the file is not a standard format (e.g., a Word Document or Excel sheet), the app parses the ASN.1 structure to extract the largest data block, recovering virtually any file type.</li>
<li><strong>Batch Processing & ZIP Export</strong>: Drag and drop dozens of <code>.p7m</code> files at once. Extract them all simultaneously and download them in a single, neat <code>.zip</code> archive.</li>
<li><strong>Modern UI/UX</strong>: Built with Tailwind CSS, featuring smooth animations, drag-and-drop support, and an adaptive Light/Dark mode.</li>
</ul>

<h2>🛠️ How it works</h2>
<ol>
<li><strong>Drag and drop</strong> your <code>.p7m</code> files into the designated dropzone.</li>
<li>The app spins up a <strong>Web Worker</strong> to prevent the UI from freezing while processing large files.</li>
<li>Instead of using heavy, error-prone cryptographic libraries, the worker reads the raw bytes (<code>Uint8Array</code>) of the file.</li>
<li>It scans the binary data looking for "Magic Bytes" (specific hex sequences) to identify the start and end of known file formats (PDF, XML, EML).</li>
<li>If the magic bytes are missing, it uses a lightweight ASN.1 parser to locate the largest <code>OCTET STRING</code>, effectively stripping away the digital certificate wrapper.</li>
<li>The app generates local <code>Blob</code> objects and renders a clean results table for individual or bulk downloads.</li>
</ol>

<h2>🏆 What makes it special?</h2>
<ul>
<li><strong>No Crypto-Library Dependencies</strong>: Most <code>.p7m</code> extractors rely on OpenSSL or Forge.js, which often fail and throw errors if the certificate is technically invalid. By doing a byte-level scan, this tool achieves a near 100% success rate.</li>
<li><strong>Zero Server Bottlenecks</strong>: By running entirely client-side, there are no file size limits (like Vercel's 4.5MB limit) and zero hosting costs for file processing.</li>
</ul>

<h2>💡 Why use this tool?</h2>
<ul>
<li><strong>Accountants & Lawyers</strong>: Effortlessly open digitally signed electronic invoices (FatturaPA) or legal acts without needing clunky smart-card software.</li>
<li><strong>Public Administration Users</strong>: Quickly read digitally signed documents for public tenders, competitions, and PEC (Certified Email) receipts.</li>
<li><strong>Everyday Users</strong>: Stop searching for suspicious "online p7m openers" that might steal your sensitive documents. Do it safely, instantly, and locally.</li>
</ul>

<h2>⚡ Getting Started</h2>

<h3>Online</h3>
<p>Simply visit the <a href="https://r0mb0.github.io/Local_p7m_extractor/">Live Demo hosted on GitHub Pages</a>.</p>

<h3>Local Installation (Fully Offline)</h3>
<p>Running this tool locally without the internet is extremely easy:</p>
<ol>
<li><strong>Clone this repository</strong> or download the source code ZIP.</li>
<li>Ensure the three core libraries are in the same folder as the HTML file (<code>tailwindcss.js</code>, <code>jszip.min.js</code>, <code>lucide.min.js</code>).</li>
<li>Double-click <code>index.html</code> to open it in your favorite browser.</li>
<li>Start extracting!</li>
</ol>

<h2>🙏 Credits & Inspiration</h2>

<ul>
<li><strong><a href="https://tailwindcss.com/" target="_blank">Tailwind CSS</a></strong>: For making the UI beautiful, responsive, and adaptive with minimal effort.</li>
<li><strong><a href="https://stuk.github.io/jszip/" target="_blank">JSZip</a></strong>: For enabling seamless, client-side ZIP archive generation.</li>
<li><strong><a href="https://lucide.dev/" target="_blank">Lucide Icons</a></strong>: For the clean, modern, and lightweight icon set.</li>
</ul>

<a href="https://github.com/R0mb0/Crafted_with_AI">
<picture>
<source media="(prefers-color-scheme: dark)" srcset="https://github.com/R0mb0/Crafted_with_AI/blob/main/Badge/SVG/CraftedWithAIDark.svg">
<source media="(prefers-color-scheme: light)" srcset="https://github.com/R0mb0/Crafted_with_AI/blob/main/Badge/SVG/NotMadeByAILight.svg">
<img alt="Not made by AI" src="https://github.com/R0mb0/Crafted_with_AI/blob/main/Badge/SVG/NotMadeByAIDefault.svg">
</picture>
</a>

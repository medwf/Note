Here are several JavaScript packages that can generate PDF files from HTML, along with their installation and basic usage examples:

---

### **1. html2pdf.js**  
**Description**: A client-side library that converts HTML to PDF using `html2canvas` and `jsPDF`. It's lightweight and easy to use.  
**Installation**:  
```bash
npm install html2pdf.js
```
**Usage Example**:  
```javascript
import html2pdf from 'html2pdf.js';

const element = document.getElementById('content-to-export');
const options = {
  margin: 10,
  filename: 'output.pdf',
  image: { type: 'jpeg', quality: 0.98 },
  html2canvas: { scale: 2 },
  jsPDF: { unit: 'mm', format: 'a4', orientation: 'portrait' }
};

html2pdf().set(options).from(element).save();
```
**Key Features**:  
- Works entirely in the browser.  
- Supports custom margins, page size, and image quality .  

---

### **2. Puppeteer**  
**Description**: A Node.js library that controls headless Chrome to generate high-fidelity PDFs from HTML.  
**Installation**:  
```bash
npm install puppeteer
```
**Usage Example**:  
```javascript
const puppeteer = require('puppeteer');

async function generatePDF(htmlContent, outputPath) {
  const browser = await puppeteer.launch();
  const page = await browser.newPage();
  await page.setContent(htmlContent);
  await page.pdf({ path: outputPath, format: 'A4' });
  await browser.close();
}

generatePDF('<h1>Hello PDF!</h1>', 'output.pdf');
```
**Key Features**:  
- Server-side generation with precise rendering.  
- Supports dynamic HTML, CSS, and JavaScript .  

---

### **3. jsPDF (+ html2canvas)**  
**Description**: A flexible library for generating PDFs. Combined with `html2canvas`, it can convert HTML to PDF.  
**Installation**:  
```bash
npm install jspdf html2canvas
```
**Usage Example**:  
```javascript
import { jsPDF } from 'jspdf';
import html2canvas from 'html2canvas';

const element = document.getElementById('content');
html2canvas(element).then((canvas) => {
  const imgData = canvas.toDataURL('image/png');
  const pdf = new jsPDF('p', 'mm', 'a4');
  pdf.addImage(imgData, 'PNG', 0, 0, 210, 297);
  pdf.save('output.pdf');
});
```
**Key Features**:  
- Works in both Node.js and browsers.  
- Supports custom fonts and vector graphics .  

---

### **4. pdfmake**  
**Description**: A declarative PDF generator that uses JSON-like structures for layout.  
**Installation**:  
```bash
npm install pdfmake
```
**Usage Example**:  
```javascript
const pdfMake = require('pdfmake/build/pdfmake');
const vfsFonts = require('pdfmake/build/vfs_fonts');

pdfMake.vfs = vfsFonts.pdfMake.vfs;

const docDefinition = {
  content: [
    { text: 'PDF from HTML-like structure', style: 'header' },
    { text: 'This is a sample PDF generated with pdfmake.' }
  ]
};

pdfMake.createPdf(docDefinition).download('output.pdf');
```
**Key Features**:  
- No HTML parsing; uses structured objects.  
- Supports tables, lists, and custom fonts .  

---

### **5. Playwright**  
**Description**: Similar to Puppeteer but supports multiple browsers (Chromium, Firefox, WebKit).  
**Installation**:  
```bash
npm install playwright
```
**Usage Example**:  
```javascript
const { chromium } = require('playwright');

(async () => {
  const browser = await chromium.launch();
  const page = await browser.newPage();
  await page.setContent('<h1>Hello PDF!</h1>');
  await page.pdf({ path: 'output.pdf' });
  await browser.close();
})();
```
**Key Features**:  
- Cross-browser compatibility.  
- Supports advanced PDF options like headers/footers .  

---

### **Comparison Table**  
| Library       | Environment  | Key Strengths                          | Limitations                          |
|--------------|-------------|---------------------------------------|--------------------------------------|
| **html2pdf.js** | Browser     | Easy setup, client-side                | Limited to simple layouts            |
| **Puppeteer**   | Node.js     | High-fidelity rendering                | Requires server-side execution       |
| **jsPDF**       | Both        | Customizable, supports fonts          | Needs `html2canvas` for HTML export  |
| **pdfmake**     | Both        | Declarative JSON structure            | No direct HTML parsing               |
| **Playwright**  | Node.js     | Multi-browser support                 | Slower than Puppeteer                |

For **client-side** needs, `html2pdf.js` or `jsPDF` are ideal. For **server-side**, `Puppeteer` or `Playwright` offer better control. Choose based on your project requirements!
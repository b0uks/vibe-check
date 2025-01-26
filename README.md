# Vibe Check

![License](https://img.shields.io/github/license/b0uks/vibe-check)
![Issues](https://img.shields.io/github/issues/b0uks/vibe-check)
![Forks](https://img.shields.io/github/forks/b0uks/vibe-check)
![Stars](https://img.shields.io/github/stars/b0uks/vibe-check)

## 📖 About

**Vibe Check** is a JavaScript-based tool designed to automatically detect and remove abusive or inappropriate content from web pages. By analyzing the text content of a webpage's body, it leverages the [ParallelDots Abuse API](https://www.paralleldots.com/abuse-detection-api) to identify and clear offensive language, ensuring a safer and more positive browsing experience.

## 🚀 Features

- **Automated Content Filtering**: Scans and processes all text nodes within a webpage to detect abusive content.
- **Real-Time Detection**: Utilizes the ParallelDots Abuse API to analyze text in real-time.
- **Seamless Integration**: Easily integrates into existing web projects or browser extensions.
- **Configurable Sensitivity**: Adjust the threshold for what constitutes abusive content based on your requirements.

## 🛠️ Installation

### Prerequisites

- **Web Browser**: Compatible with modern browsers like Chrome, Firefox, and Edge.
- **ParallelDots API Key**: Obtain an API key by signing up at [ParallelDots](https://www.paralleldots.com/).

### Clone the Repository

```bash
git clone https://github.com/b0uks/vibe-check.git
cd vibe-check
```
Setup
Insert the Script into Your Project

Copy the vibe-check.js file into your project directory.

Include the Script in Your HTML

Add the following script tag to your HTML file, preferably before the closing </body> tag:

```html
<script src="path/to/vibe-check.js"></script>
```
Configure the API Key

Replace the placeholder API key in the script with your actual ParallelDots API key:

```javascript
let params = 'text=' + encodeURIComponent(txt) + '&api_key=YOUR_PARALLELDOTS_API_KEY';
```

⚠️ Important: For security reasons, avoid exposing your API key in client-side code. Consider implementing server-side proxying to keep your API key secure.

⚙️ Usage
Once integrated, the script will automatically scan the text content of the webpage's body and remove any content flagged as abusive based on the defined threshold.

How It Works
Deep Text Extraction: The deepText function recursively traverses the DOM to collect all text nodes within the <body> tag.
Abuse Detection: For each text node, the script sends the text to the ParallelDots Abuse API.
Content Removal: If the API response indicates that the text is abusive (i.e., response['abusive'] > 0.5), the script clears the content of that text node.
Example
```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Vibe Check Example</title>
</head>
<body>
  <p>This is a sample paragraph.</p>
  <p>This text contains abusive language.</p>

  <script src="vibe-check.js"></script>
</body>
</html>
```
In the above example, any paragraph containing abusive language will be cleared automatically upon page load.

📁 Project Structure
```sql
vibe-check/
├── vibe-check.js
├── README.md
└── LICENSE
```

vibe-check.js: Main JavaScript file containing the content filtering logic.
README.md: Project documentation.
LICENSE: Licensing information.
🧪 Testing
To ensure the script works as expected:

1. Open the HTML File

Load your HTML file in a web browser.

2. Check the Console

Open the browser's developer console to view logs related to API responses and content removal actions.

3. Verify Content Removal

Inspect the webpage to confirm that abusive content has been cleared.


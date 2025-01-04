# Interactive Web Element Inspector Script

This JavaScript script allows you to inspect and interact with web elements on a page, view their HTML and CSS, and easily copy them to your clipboard. It also provides a simple action menu to display and copy the HTML and CSS of elements on hover and click.

## Features
- Hover over elements to highlight them.
- View HTML and CSS data for any element by clicking on it.
- Copy HTML, CSS, or both to your clipboard.
- View a rendered preview of the clicked element.
- Option to close the action menu.

![Element Style Extractor](https://github.com/ayushgupta9906/Element-Style-Extractor/blob/sae/IMG.jpg)

## Methods to Run the Script

### Method 1: Running the Script in the Browser Console

You can run the script directly in your browser’s developer console.

#### Steps:
1. Open the website where you want to run the script (or your local web page).
2. Open the browser's Developer Tools:
   - **Google Chrome**: Press `Ctrl + Shift + I` (or `Cmd + Option + I` on Mac) or right-click on the page and select **Inspect**.
   - **Mozilla Firefox**: Press `Ctrl + Shift + I` (or `Cmd + Option + I` on Mac) or right-click and select **Inspect**.
   - **Microsoft Edge**: Press `F12` or right-click and select **Inspect**.
3. Go to the **Console** tab.
4. Copy the entire JavaScript code from the `script.js` file and paste it into the console.
5. Press **Enter** to execute the script.

#### How to Use:
- Hover over elements to highlight them with a red outline.
- Click on any element to open the action menu, where you can:
  - Copy the HTML and/or CSS to your clipboard.
  - View a rendered preview of the clicked element.
  - Close the action menu.

### Method 2: Running the Script as a Browser Extension

If you'd prefer to use this as a browser extension, follow the steps below to load it as an extension in **Google Chrome** (similar steps can be followed for **Firefox**).

#### Steps:
1. Create a new folder and name it `web-element-inspector`.
2. Inside the folder, create the following files:
   - `manifest.json`
   - `script.js`

#### 1. `manifest.json` file:

```json
{
  "manifest_version": 2,
  "name": "Web Element Inspector",
  "description": "Inspect and copy HTML & CSS of web elements.",
  "version": "1.0",
  "permissions": [
    "activeTab"
  ],
  "browser_action": {
    "default_popup": "popup.html",
    "default_icon": {
      "16": "icon.png",
      "48": "icon.png",
      "128": "icon.png"
    }
  },
  "background": {
    "scripts": ["script.js"],
    "persistent": false
  },
  "icons": {
    "16": "icon.png",
    "48": "icon.png",
    "128": "icon.png"
  },
  "content_scripts": [
    {
      "matches": ["<all_urls>"],
      "js": ["script.js"]
    }
  ]
}

## 🚀 AI Launchpad: Static AI Tool Showcase

A simple, fast, and lightweight web application designed to showcase a curated list of AI tools. All data is loaded from a local `data.csv` file, making the site 100% static and perfect for hosting on platforms like GitHub Pages.

The project features dynamic category filtering and clean, slug-based URL deep linking.

### ✨ Features

* **Static & Portable:** Runs entirely client-side (HTML/CSS/JS). No backend needed.
* **CSV Data Source:** Easily manage your list by editing a single `data.csv` file.
* **Dynamic Category Filtering:** Instantly filter the list using category buttons derived from your data.
* **Slug-Based Deep Linking:** Share clean, readable URLs to specific categories (e.g., `...#video-editing`).
* **Favicon Fallback:** Automatically fetches favicons for each listed website, falling back to a text initial if the favicon is unavailable.
* **Modern Design:** Uses Tailwind CSS for a clean, responsive, and professional look.

### 🛠️ Setup and Usage

This project requires only two files in the root of your repository: `index.html` (the file I provided) and `data.csv`.

#### 1. The Data File (`data.csv`)

The application expects a comma-separated value file with exactly four columns, including a header row.

| Header Row | Example Data | Description |
| :--- | :--- | :--- |
| **Category** | `Writing` | Used for filtering and tagging. |
| **Tool Name** | `Gemini Pro` | The primary title of the tool. |
| **Website** | `https://gemini.google.com/` | The full URL for the "Visit" button. |
| **Description** | `"The most powerful AI model for text generation."` | A brief, punchy summary. |

**Example `data.csv` Structure:**

```csv
Category,Tool Name,Website,Description
Writing,Gemini Pro,[https://gemini.google.com/](https://gemini.google.com/),"The most powerful AI model for text generation."
Video Editing,Descript,[https://www.descript.com/](https://www.descript.com/),"Edit video by editing text. Fast, easy, and collaborative."
Audio & Music,Suno AI,[https://www.suno.ai/](https://www.suno.ai/),"Create full, finished songs from a single prompt."
```

#### 2. Local Preview (macOS/Linux)

To preview the project locally, you must use a simple HTTP server to avoid CORS errors when fetching the data.csv file.

* Open your terminal.
* Navigate to the project folder:`cd /path/to/your/repo/`
* Start the Python 3 simple web server: `python3 -m http.server`
* Open your browser and navigate to: http://localhost:80003.

**Hosting on GitHub Pages**

This project is optimized for GitHub Pages.Create a new GitHub Repository (e.g., ai-launchpad).Push index.html and data.csv to the main branch.Navigate to Settings > Pages.Set the source to Deploy from a branch and select the main branch and the / (root) folder.Click Save. Your site will be live within a few minutes.

### 🔗 Deep Linking (Slugging) Explained

The application uses URL hashing to enable shareable links to filtered categories. This works because of the custom slugging logic which converts categories from the CSV into URL-friendly slugs

|Original Category (in CSV)|URL Slug (in hash)|Example URL|
|---|---|---|
|Audio & Music|audio-music|.../index.html#audio-music|
|Writing/Coding|writing-coding|.../index.html#writing-coding|
|Image Generation|image-generation|.../index.html#image-generation|

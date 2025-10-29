# PixelStash - A Pinterest-Style Image Explorer

PixelStash is a modern, responsive, and secure single-page application (SPA) that provides a Pinterest-style masonry grid for exploring high-quality stock photos. It is built with modern web technologies, focusing on a seamless user experience, performance, and robust security.

**[Live Demo](https://your-project-name.vercel.app)** (Replace with your Vercel URL)

![PixelStash Screenshot](https://via.placeholder.com/800x500.png?text=PixelStash+App+Screenshot)

---

## ✨ Core Features

*   **Infinite Scroll Masonry Layout:** Images are displayed in a beautiful, Pinterest-like grid that loads more content as you scroll.
*   **Powerful Image Search:** Utilizes the Pexels API to search through millions of high-quality, royalty-free images.
*   **Image Detail View:** Click on any image to view it in a larger modal, complete with its description and related images.
*   **Personal Profiles & Collections:** Save your favorite images to a personal profile, with all data persisted in the browser's LocalStorage.
*   **Seamless SPA Routing:** A custom routing hook provides fast, client-side navigation without page reloads.
*   **Web Share & Copy Link:** Easily share images using the native Web Share API or copy a direct link to the clipboard.
*   **Customizable UI:** Users can adjust preferences, such as the image hover effect, via a settings modal.
*   **SEO Optimized:** Dynamically generated meta tags and JSON-LD structured data for every page to ensure excellent search engine visibility.

## 🛠️ Technology Stack

This project is built directly in the browser using modern web standards and CDN-hosted libraries, requiring no local build step.

*   **Frontend:** [React 19](https://react.dev/), [TypeScript](https://www.typescriptlang.org/)
*   **Styling:** [Tailwind CSS](https://tailwindcss.com/) (via CDN)
*   **Image Data:** [Pexels API](https://www.pexels.com/api/)
*   **AI Suggestions:** [Google Gemini API](https://ai.google.dev/) (for generating related search themes)
*   **Deployment:** [Vercel](https://vercel.com/)

---

## 🚀 Getting Started

### Prerequisites

*   A modern web browser (Chrome, Firefox, Safari, Edge).
*   A code editor (like VS Code).
*   A local web server to serve the files.

### Running Locally

Because this project uses ES modules, you need to run it from a local web server to avoid CORS errors. You can use any simple server; the `serve` package is a great option.

1.  **Clone the repository:**
    ```bash
    git clone https://github.com/your-username/pixelstash.git
    cd pixelstash
    ```

2.  **Set up Environment Variables:**
    This project requires an API key from Pexels.
    *   Get a free API key from [Pexels API](https://www.pexels.com/api/getting-started/).
    *   **Note:** In a typical project, you would create a `.env` file. For this browser-only setup, the `PEXELS_API_KEY` is expected to be available as an environment variable in the deployment environment (e.g., Vercel). To run locally, you may need to temporarily hardcode it or use a tool that can serve files with environment variable injection.

3.  **Serve the project:**
    If you have Node.js installed, you can use the `serve` package:
    ```bash
    # Install serve globally if you haven't already
    npm install -g serve

    # Run the server from the project's root directory
    serve
    ```
    The server will start, and you can open the provided URL (usually `http://localhost:3000`) in your browser.

---

## 🔒 Security Features

This application was built with security as a priority, implementing several best practices:

*   **Content Security Policy (CSP):** A strict CSP is enforced via meta tags to prevent XSS attacks by restricting which scripts, styles, and other resources can be loaded.
*   **Secure HTTP Headers:** Includes `X-Content-Type-Options`, `X-Frame-Options`, and `Referrer-Policy` to protect against clickjacking and content sniffing and to enhance user privacy.
*   **Search Abuse Prevention:** The search input is limited to 256 characters to prevent overly long queries.
*   **Secure Image Proxy Pattern:** The client-side code is architected to route image downloads through a secure backend proxy (the service is included, but the backend endpoint would need to be implemented for a full production setup).
*   **SPA Routing on Production:** A `vercel.json` file is included with the correct rewrite rules to ensure client-side routing works correctly on refresh, preventing 404 errors.

---

## 🌐 Deployment

This project is optimized for deployment on [Vercel](https://vercel.com/).

1.  **Push your project to a GitHub repository.**
2.  **Import the repository into Vercel.** Vercel will automatically detect that it is a static site. No build command is necessary.
3.  **Configure Environment Variables:** In your Vercel project settings, go to the "Environment Variables" section and add your Pexels API key:
    *   **Name:** `PEXELS_API_KEY`
    *   **Value:** `your_actual_pexels_api_key_here`

Vercel will automatically deploy your project. Any subsequent pushes to your main branch will trigger new deployments.

## 📄 License

This project is licensed under the MIT License. See the `LICENSE` file for details.

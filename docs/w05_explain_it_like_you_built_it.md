# Explain It Like You Built It: How GitHub Pages Automatically Deploys My Portfolio Site

**Track:** General AI Fluency | **Phase:** Build+  
**Assignment:** Explain It Like You Built It (Week 5)

---

## 1. The Component I Chose to Own

When setting up my machine learning portfolio on GitHub Pages using MkDocs, the part that initially felt like "magic" was **how pushing code to GitHub automatically builds and updates the live website**. 

I wanted to understand the exact link between committing a Markdown file (`.md`) on my laptop and having it show up rendered with styles, navigation, and HTML on my live URL.

---

## 2. Plain-English Explanation (Teaching a Peer)

Imagine you are writing a book in a raw text document on your laptop. Every time you finish a page, you don't manually print, bind, and ship the physical book to a bookstore yourself. Instead, you drop your text file into a specialized digital publishing house.

Here is how that exact process works for my website step-by-step:

1. **The Raw Source (My Markdown Files):** 
   I write my machine learning case studies and documentation in standard Markdown (`.md`) files inside the `docs/` folder of my repository. Markdown is just text with simple symbols—like `#` for headers or `**` for bold text. It is not an active website yet.

2. **The Git Push Signal:** 
   When I run `git push origin main`, I am sending a notification to GitHub saying: *"Hey, I just saved new updates to the main folder."*

3. **The Automated Publishing Factory (GitHub Actions):** 
   GitHub receives the push and triggers an automated script behind the scenes called a **GitHub Action**. This script spins up a temporary virtual computer in the cloud that performs three jobs:
   * It installs **MkDocs** and the **Material theme**.
   * It reads all my `.md` files and translates them into styled HTML, CSS, and JavaScript files (the format browsers actually read).
   * It packages those generated HTML files and places them onto a hidden branch in my repository named `gh-pages`.

4. **Serving the URL:** 
   GitHub Pages points a web server directly to that `gh-pages` branch. The web server takes those generated static HTML files and makes them publicly accessible at my personal domain link: `https://ayesharizz321-ai.github.io/flyrank-ml--internship/`.

---

## 3. Why This Matters & Key Takeaway

Understanding this flow took away the black-box confusion. I now know that if my live site breaks or fails to update:
* It isn't a browser glitch.
* I can check the **Actions** tab in my GitHub repository to see if the static site compilation step failed (for instance, due to a broken link or YAML formatting error in `mkdocs.yml`).

I am not just copying code—I own the exact deployment pipeline that publishes my data science portfolio to the web.

---

## 4. Pass / Revise Verification Checklist

- [x] **Real Build Component:** Explains the exact GitHub Pages / MkDocs deployment pipeline used for this portfolio.
- [x] **Plain-Words Explanation:** Written in an authentic, conversational style as if teaching a classmate.
- [x] **Demonstrates Genuine Learning:** Clear separation between source code (`.md`), compilation tool (`MkDocs`), and web serving (`GitHub Pages`).
-

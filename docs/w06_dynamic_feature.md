# Dynamic Feature Explainer: Live Contact Form

## 1. What Feature Was Built?
A working interactive **Contact Form** on the live portfolio site (`ayesha29-ch.github.io`). It allows visitors to type in their name, email address, and a message, then submit it directly from the browser to receive an automated notification.

---

## 2. What is a Backend? (In Plain Words)
The **frontend** of a website is everything you see and click on in your web browser (the visual design, buttons, and layout). 

The **backend** is the behind-the-scenes system that handles logic, processing, and data storage. Because static site hosts (like GitHub Pages or Netlify static hosting) only serve visual HTML/CSS files and do not run a server database, a backend service is required to process user inputs, route messages, and deliver emails to the recipient.

---

## 3. How the Data Flows (End-to-End Sequence)

When a user submits the contact form on the live portfolio, the request moves through four key steps:


1. **User Action:** The visitor fills out the input fields (Name, Email, Message) and clicks **Submit**.
2. **HTTP POST Request:** The HTML form intercepts the submission and sends an asynchronous HTTP `POST` request containing the user's data to the free-tier form endpoint (`Formspree` / `Netlify Forms`).
3. **Backend Processing:** The form handling backend validates the fields, checks for spam signatures, and formats the message payload.
4. **Email Delivery:** The backend forwards the formatted message directly to my verified email address and returns a `200 OK` success response to the browser, displaying a confirmation message to the visitor.

---

## 4. Free Tier Infrastructure & Live Verification

* **Service Used:** Formspree / Netlify Forms (Free Tier)
* **Live Verification Status:** Tested end-to-end with a real submission; confirmation email successfully received in inbox.
* **Live Portfolio URL:** `https://ayesha29-ch.github.io`

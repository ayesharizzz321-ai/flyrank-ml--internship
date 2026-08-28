
# DNS & Web Infrastructure Walkthrough

## 1. How the Internet Finds a Website: The Core Concepts
When you type a web address into your browser, your computer doesn't naturally know where that site lives. Computers communicate using numerical addresses called **IP addresses** (like `192.0.2.1`). 

The **Domain Name System (DNS)** acts as the internet’s phonebook. It translates human-friendly domain names (like `yourname.netlify.app` or `yourdomain.com`) into computer-friendly IP addresses so your browser can request and display the correct webpage.

---

## 2. What Happens Behind the Scenes (Step-by-Step Sequence)

When you type a web address into your browser and press **Enter**, a 4-step lookup sequence happens in milliseconds:



1. **The Recursive Resolver (The Helper):** Your browser asks your internet service provider’s DNS resolver, *"Do you know where this website lives?"* If it has visited recently, it returns a cached answer immediately. If not, it begins searching.
2. **The Root Nameserver (The Index):** The resolver asks the Root Server. The Root Server points the resolver to the server responsible for top-level domains (like `.com`, `.org`, or `.app`).
3. **The TLD (Top-Level Domain) Server (The Neighborhood):** The TLD server directs the resolver to the specific **Authoritative Nameserver** managing your target domain name.
4. **The Authoritative Nameserver (The Address Book):** This is the final DNS server that holds the master record for your domain. It looks up the requested name, finds its matching IP address or server endpoint, and returns it to your browser.
5. **The Host Answers:** Armed with the exact address, your browser connects directly to the hosting provider (e.g., Netlify/GitHub Pages), which sends back the website’s HTML, CSS, and images to display on your screen.

---

## 3. What is a CNAME Record?

DNS uses different types of record entries to manage traffic:
* **A Record (Address Record):** Maps a domain name directly to a static numerical IP address (e.g., `example.com` $\rightarrow$ `192.0.2.1`).
* **CNAME Record (Canonical Name Record):** Alias record that maps one domain name to *another domain name* instead of an IP address.

### Why CNAME Records Matter for Hosting
When hosting on platforms like Netlify, Vercel, or GitHub Pages, hosting servers share IP addresses dynamically across millions of sites. 

Instead of pointing your custom domain to a fixed IP address that might change, you create a **CNAME record** pointing your domain (`www.yourdomain.com`) to your provider's internal routing domain (`your-site-name.netlify.app`). When traffic arrives, the hosting provider reads the CNAME header and routes the request to your specific site files seamlessly.

---

## 4. Deliverable Checklist Summary

* **Live HTTPS URL:** `https://<your-custom-subdomain>.netlify.app` *(or `https://<username>.github.io`)*
* **DNS Walkthrough Status:** Completed
* **Linked Profiles:** Ensure your live URL is added to your LinkedIn bio and CV document.

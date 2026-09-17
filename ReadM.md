### DNS & CNAME Walkthrough

**1. What is DNS?**
The Domain Network System (DNS) acts as the phonebook of the internet. It translates human-readable domain names (like `example.netlify.app`) into machine-readable IP addresses (like `192.0.2.1`) so browsers can load web resources.

**2. What is a CNAME Record?**
A Canonical Name (CNAME) record is a type of DNS record used to alias one domain name to another. Instead of pointing directly to an IP address, a CNAME points a subdomain (e.g., `www.yourname.com`) to your primary hosting provider's URL (e.g., `yourname.netlify.app`), ensuring that even if the host's IP changes, your link remains valid.

**3. What Happens When You Type a Website Address:**
* **Browser Request:** When you type a URL and hit Enter, your browser first checks its local cache to see if it already knows the IP address.
* **Recursive Resolver:** If not cached, the request goes to a DNS resolver (usually managed by your Internet Service Provider or a service like Cloudflare).
* **Root and TLD Servers:** The resolver queries Root servers and Top-Level Domain (TLD) servers to find out which authoritative nameserver holds the records for that domain.
* **Authoritative Nameserver & Response:** The resolver queries the authoritative nameserver, which returns the correct IP address or CNAME record. The resolver sends this back to your browser, allowing it to connect to the web host and load the page over HTTPS.
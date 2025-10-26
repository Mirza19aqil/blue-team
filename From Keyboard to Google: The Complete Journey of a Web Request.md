<p align="center">
  <b>Behind the Scenes: What Happens When You Type google.com</b>
</p>

when you enter www.google.com, your browser begins long chains of tecnical action to convert this name into an ip address.

The browser first checks if it already knows the IP address for www.google.com from a previous visit.
If found, it uses that IP (this is called a DNS cache hit) and skips DNS lookup.
If not found, it continues to the next step.

Your computer’s OS (like Windows or Linux) also keeps a cache of previously resolved domains.
If the IP address of www.google.com is in that cache, it’s used directly.

If not found, your OS sends a DNS query to your configured DNS resolver (usually your ISP or a public resolver like Google’s 8.8.8.8 or Cloudflare’s 1.1.1.1

If the DNS resolver doesn’t know the IP, it performs recursive lookups:
Root DNS Server:
Resolver asks a root server: “Who handles .com domains?”
TLD Server (.com):
Root replies with the IP of a Top-Level Domain (TLD) server for .com.
Resolver then asks that server: “Who handles google.com?”
Authoritative DNS Server (for Google):
The .com TLD server points to Google’s own DNS servers.
They reply with the IP address for www.google.com (for example, 142.250.191.4).
Now the resolver returns this IP to your OS, which passes it to the browser.
This process is called DNS resolution and usually takes only a few milliseconds

Now your browser knows Google’s IP address.
Next step: open a TCP connection to the Google server.
Your system sends a TCP SYN packet to 142.250.191.4 on port 443 (HTTPS).
Google’s server replies with a SYN-ACK (acknowledgment).
Your system replies with an ACK.
This is the TCP 3-way handshake — now a connection is established

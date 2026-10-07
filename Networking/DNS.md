# How DNS Finds the IP Address of a Website?

We learned how DHCP (Dynamic Host Configuration Protocol) automatically gives a device an IP address, subnet mask, default gateway, and DNS server information when it joins a network.

After DHCP completes, your computer is connected to the network.

Now imagine you open your browser and type:

`www.google.com`

Your computer understands IP addresses, not website names.

So how does it find Google’s server?

This is where DNS (Domain Name System) comes in.

---
---

## What is DNS?

DNS (Domain Name System) is a distributed system that translates human-readable domain names into IP addresses.

### Examples:

| Domain Name | IP Address |
|--------------|------------|
| www.google.com | 142.250.x.x |
| www.youtube.com | 142.250.x.x |
| www.microsoft.com | 20.x.x.x |

*(The exact IP addresses may change over time.)*

Instead of remembering numbers, we simply remember website names.

Think of DNS as the Internet’s phonebook.

Instead of storing phone numbers, it stores IP addresses.

---
---

## Why Do We Need DNS?

Imagine if DNS didn’t exist.

Instead of typing:

- `www.google.com`

you would need to type something like:

- `142.250.190.78`

Now imagine remembering the IP addresses of hundreds of websites.

**Clearly, that isn’t practical.**

### DNS solves this problem by translating website names into IP addresses automatically.

#### Example Network
We’ll continue using the same home network from Part 1.

| Device | IP Address |
|---------|--------------|
| Router (Gateway) | 192.168.1.1 |
| Laptop | 192.168.1.10 |
| DNS Server (Recursive Resolver) | 8.8.8.8 |

In many home networks, the recursive resolver is provided by the Internet Service Provider (ISP). In this example, we use Google’s public DNS server (`8.8.8.8`) as the recursive resolver.

Suppose the user enters:

- `www.google.com`

The laptop now needs to discover Google’s IP address.

---
---

## DNS Lookup Process

### Step 1: Browser Checks Its DNS Cache
Before sending any network request, the browser first checks whether it already knows the IP address.

**For example:**

```
www.google.com
      ↓
142.250.xx.xx
```
If the entry exists and hasn’t expired, the browser immediately uses the cached IP address.

*No DNS query is needed.*

This makes websites load faster.

---

### Step 2: Operating System Checks Its DNS Cache
If the browser doesn’t have the answer, the operating system checks its own DNS cache.

Windows, Linux, and macOS all maintain a DNS cache.

If the IP address is found here, the operating system returns it to the browser.

*Again, no network request is required.*

---

### Step 3: Check the Hosts File
If the DNS cache doesn’t contain the answer, the operating system checks the hosts file.

The hosts file allows domain names to be mapped manually to IP addresses.

**For example:**

```
192.168.1.50   myserver.local
127.0.0.1      localhost
```
Developers often use this file for testing.

If a matching entry exists, DNS is skipped entirely.

---

### Step 4: Send a DNS Query

If no cached information is available, the operating system sends a DNS query to the DNS server received from DHCP.

#### For our example:

**DNS Server:**
- `8.8.8.8`

**The query asks:**
> "What is the IP address of www.google.com?"

## DNS typically uses:
- **UDP Port 53** — Used for most DNS queries because it has lower overhead and is faster.
- **TCP Port 53** — Used when responses are too large for UDP, for DNS zone transfers, or in certain other situations.

Most everyday lookups use UDP because it is faster and has lower overhead.

## Recursive Resolver (or DNS Resolver)
The DNS server configured on your computer is called a recursive resolver. In many networks, this resolver is operated by your ISP. In this example, we use Google’s public DNS server (`8.8.8.8`) as the recursive resolver.

A **DNS Resolver** is a server that acts as a middleman between a user and the DNS infrastructure. Its job is to find the answer on your behalf. Instead of your computer contacting multiple DNS servers across the internet, it sends a single query to the recursive resolver. The resolver performs the remaining work.

---
---

## How the Resolver Finds the Answer

If the resolver already has the answer cached, it immediately returns it.

Otherwise, it performs a sequence of DNS lookups. The resolver also caches information about root and TLD servers, so future lookups often skip some of these steps.

---

### Step 1: Root Name Server
The resolver first contacts a Root Name Server.

The root server doesn’t know the IP address of every website. Instead, it tells the resolver which `.com` Top-Level Domain (TLD) name servers are responsible for the `.com` domain.

It essentially replies:

> “I don’t know the IP address, but these `.com` TLD name servers can help you.”

---

### Step 2: TLD Name Server
The resolver now contacts one of the `.com` Top-Level Domain (TLD) name servers.

The TLD server does not know the IP address of `www.google.com`. Instead, it knows which authoritative name servers are responsible for the `google.com` domain.

It replies with the names (and, if needed, the IP addresses) of Google’s authoritative name servers.

It essentially replies:

> “I don’t know Google’s IP address, but these are Google’s authoritative name servers.”

---

## Step 3: Authoritative Name Server

The resolver now contacts one of Google’s authoritative name servers.

This server stores the official DNS records for the `google.com` domain. It returns the requested DNS record, such as an A record (IPv4) or AAAA record (IPv6), containing the IP address for `www.google.com`.

### Example:

```
www.google.com
      ↓
142.250.xx.xx
```

---

### Step 4: DNS Response

The recursive resolver sends the IP address back to your computer.

- The operating system stores it in its DNS cache for a limited time.
- The browser also stores it in its own cache.

Future visits to the same website can often skip the DNS lookup until the cached entry expires.

<img width="720" height="432" alt="image" src="https://github.com/user-attachments/assets/4b20d683-a33c-48c8-89fd-495a78ecb660" />

---

## What is TTL?

Every DNS record includes a value called **TTL (Time To Live)**.

### Example:

- TTL = 300 seconds

This tells devices how long they may cache the DNS record.

When the TTL expires, a new DNS lookup is performed.

**TTL helps balance performance with keeping DNS information up to date.**

---

Complete DNS Flow
```
User enters
www.google.com
        │
        ▼
Browser DNS Cache
        │
        ▼
OS DNS Cache
        │
        ▼
Hosts File
        │
        ▼
Recursive DNS Resolver (8.8.8.8)
        │
        ▼
Resolver Cache?
        │
        ├── Yes → Return IP Address
        │
        └── No
             │
             ▼
      Root Name Server
             │
             ▼
      .com TLD Name Server
             │
             ▼
Google Authoritative Name Server
             │
             ▼
Returns A/AAAA Record
             │
             ▼
IP Address Returned
             │
             ▼
Browser now knows where Google's server is
```

---

## How Authoritative Name Server Knows the Domain Information?

An authoritative name server doesn’t discover domain information. It already has it stored.

The domain owner or DNS provider puts all the records (like IP address, mail servers, etc.) into a DNS zone file, and that file is loaded into the authoritative server.

So when someone asks for a domain, the server simply replies with the data it already has — because it is the official source for that domain, not a lookup system.

### Examples:
- Amazon Web Services (Route 53)
- Google Cloud (Cloud DNS)
- GoDaddy
- Namecheap
- Cloudflare

---


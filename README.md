# Best VPS for WordPress Hosting: Tired of Slow Shared Plans? Here's How to Pick a VPS That Won't Quit on You — Speed, PHP 8.3, MySQL 8, Pricing Compared (Plus BandwagonHost Plan Picks)

## Why Your WordPress Site Outgrows Shared Hosting

If you've landed here searching for the **best VPS for WordPress hosting**, there's a decent chance you've already lived through the pain. Your dashboard takes ten seconds to load. A modest traffic spike from a single tweet turns your homepage into a slideshow. Support tickets get answered with the same copy-pasted line about "resource limits." You upgraded to the "Pro" shared tier and nothing really changed.

Here's the thing nobody on the marketing pages tells you straight: shared hosting is a flat with eight roommates and one bathroom. On a quiet Tuesday morning it's fine. On a Saturday night when everyone's home, it's not. A VPS gives you your own bathroom, your own kitchen, and a door you can actually lock.

WordPress is not a particularly heavy application by itself, but it's sneaky. The core is lean; it's the ecosystem around it — WooCommerce, Elementor, a dozen plugins, a bulky theme, image-heavy posts — that turns a $3/month shared plan into a stuttering mess. WordPress.org's current requirements ask for **PHP 8.3 or greater**, **MySQL 8.0+ or MariaDB 10.6+**, and **HTTPS**. Plenty of bargain shared hosts still ship PHP 7.4 and call it "optimized for WordPress." A real VPS lets you run the versions you actually want.

The honest reason most people delay the move is fear of the command line. That fear is reasonable but smaller than it looks. Once you're over it, the payoff is huge: predictable performance, full control over PHP versions and caching layers, the ability to install Redis or Opcache without filing a ticket, and pricing that doesn't triple on renewal.

## What Actually Makes a VPS Good for WordPress

Before picking a provider, it helps to know what you're picking for. WordPress runs on the classic LAMP or LEMP stack — Linux, Apache or Nginx, MySQL or MariaDB, PHP. The "best VPS for WordPress hosting" question is really a question about how well a provider serves that stack.

**CPU and RAM matter more than advertised disk.** WordPress with WooCommerce on a 1 GB RAM box will swap itself to death during a sale. A modest blog on the same box is perfectly happy. The honest minimums I'd run today: 1 GB RAM for a small personal blog, 2 GB for a typical multi-plugin business site, 4 GB once WooCommerce or a membership plugin enters the picture.

**Storage type is not a detail.** NVMe RAID-10 is meaningfully faster than older SATA SSD RAID-10, especially for database queries. WordPress is database-heavy; every page load is a stack of SELECTs. Faster storage shows up directly in your TTFB (time to first byte).

**PHP version support.** PHP 8.3 is roughly 20–30% faster than PHP 7.4 on real WordPress workloads. If a provider only lets you run PHP 7.4, that's a provider from 2018 wearing a fresh coat of paint. The ideal VPS gives you root, so you install the PHP your distro ships — Debian 13 and Ubuntu 26.04 both bring modern PHP by default.

**Network and location.** A VPS in a datacenter 200ms from your readers is a VPS that feels slow no matter how fast the CPU is. If your audience is global, a US west-coast location with good peering is a safe default. If your audience is in China, regular transit turns into packet-loss soup at peak hours, and you want a CN2 GIA route — more on that below.

**Backups and snapshots.** WordPress gets hacked. Plugins ship buggy updates. A host that hands you free automatic backups and snapshots is a host that has already saved you a future bad weekend.

## BandwagonHost's WordPress-Friendly Stack

This is where [BandwagonHost](https://bit.ly/BandwagonHost) enters the picture, and why it shows up in a lot of "best VPS for WordPress hosting" shortlists even though it doesn't market itself as a WordPress host at all.

BandwagonHost (often called BWH, and known to its large Chinese user base as 搬瓦工) sells **self-managed KVM VPS** running on its in-house **KiwiVM** control panel. It does not sell "WordPress hosting" as a packaged product. That's actually the point: instead of a cPanel + WordPress-button experience, you get a clean Linux box with root, and you build the stack you want. For someone who's outgrown shared hosting and is tired of the host's opinions about caching, that's a feature, not a bug.

A few things in the stack matter specifically for WordPress workloads:

- **Full root access** on every plan, so you can install PHP 8.3, Nginx, MariaDB, Redis, Opcache, and whatever WP-CLI version you like.
- **Free automatic backups and free snapshots** on every plan I looked at — even the $49.99/year entry box. That's not common at this price point.
- **20+ OS templates** including Debian 13, Ubuntu 26.04, AlmaLinux, Rocky Linux, CentOS Stream and Fedora. Modern distros ship modern PHP and MariaDB out of the box, so you're not fighting old packages.
- **Manual ISO install** option if you want to bring your own image.
- **Free datacenter migration** between locations from the panel — useful if you start in New York and later realize your readers are mostly in Asia.
- **NVMe RAID-10 storage** on the newer AMD EPYC nodes (Los Angeles DC9, Hong Kong HK3/HK8, New York). The older PROMO tier still runs SATA SSD RAID-10, which is fine but slower.
- **IPv4 + a routed IPv6 /64** on every plan, so you're not fighting for an address when you add a staging subdomain.
- **30-day refund policy** and a 99.95% uptime guarantee (99.99% on the ECommerce SLA tier).

The tradeoff to understand going in: this is **self-managed**. There is no "click here to install WordPress" button in KiwiVM. You SSH in and set things up, or you install a free panel like HestiaCP / CloudPanel / aaPanel on top and get a GUI. If the words `apt install nginx php8.3-fpm mariadb-server` make you nervous, budget an afternoon with a good tutorial, or pick a provider that sells managed WordPress hosting instead. BandwagonHost keeps prices low precisely by not doing that hand-holding.

## The Full Plan Lineup: Basic, CN2 GIA, ECommerce SLA

BandwagonHost runs three broad product families, and within each family the storage/RAM tiers step up in roughly the same shape (20G / 40G / 80G / 160G / 320G / 480G or 640G / 1280G at the top of the premium tiers). Here's the complete current lineup as listed on the official order pages, with annual-equivalent pricing where the plan bills monthly or quarterly.

### Basic KVM — PROMO VPS (the entry tier)

The cheapest family. SATA SSD RAID-10, 1 Gbps uplink, multiple datacenter locations (Los Angeles, New York, Vancouver, etc.), free migration between them. No CN2 routing — these ride regular transit, which is fine for non-China audiences.

| Plan | RAM | vCPU | SSD | Transfer | Billing | Annual equiv. | Buy |
|---|---|---|---|---|---|---|---|
| 20G KVM PROMO | 1 GB | 2x | 20 GB | 1 TB/mo | $49.99/yr | $49.99 | [Get this plan](https://bit.ly/BandwagonHost) |
| 40G KVM PROMO | 2 GB | 3x | 40 GB | 2 TB/mo | $52.99/half-yr ($99.99/yr) | $99.99 | [Get this plan](https://bit.ly/BandwagonHost) |
| 80G KVM PROMO | 4 GB | 4x | 80 GB | 3 TB/mo | $19.99/mo ($199.99/yr) | $199.99 | [Get this plan](https://bit.ly/BandwagonHost) |
| 160G KVM PROMO | 8 GB | 5x | 160 GB | 4 TB/mo | $39.99/mo ($399.99/yr) | $399.99 | [Get this plan](https://bit.ly/BandwagonHost) |
| 320G KVM PROMO | 16 GB | 6x | 320 GB | 5 TB/mo | $79.99/mo ($799.99/yr) | $799.99 | [Get this plan](https://bit.ly/BandwagonHost) |
| 480G KVM PROMO | 24 GB | 7x | 480 GB | 6 TB/mo | $119.99/mo ($1199.99/yr) | $1199.99 | [Get this plan](https://bit.ly/BandwagonHost) |

### CN2 GIA / CTGNet VPS — Hong Kong, Tokyo, Osaka, Singapore

The premium-route family, built for serving audiences in or near China. CN2 GIA (AS4809) and CTGNet (AS23764) are China Telecom's highest-quality transit, the routes that don't collapse into 30% packet loss at peak hours. Hong Kong and Tokyo share the same pricing; Singapore is slightly cheaper; Osaka sits between. Link speeds climb with the tier (1 Gbps at the low end in HK, up to 5 Gbps on the big Singapore boxes).

| Plan | RAM | vCPU | SSD | Transfer | Location | Monthly | Annual | Buy |
|---|---|---|---|---|---|---|---|---|
| 40G HK CN2 GIA | 2 GB | 2x | 40 GB | 500 GB/mo | Hong Kong HK2 | $89.99 | $899.99 | [Get this plan](https://bit.ly/BandwagonHost) |
| 80G HK CN2 GIA | 4 GB | 4x | 80 GB | 1000 GB/mo | Hong Kong HK2 | $155.99 | $1559.99 | [Get this plan](https://bit.ly/BandwagonHost) |
| 160G HK CN2 GIA | 8 GB | 6x | 160 GB | 2000 GB/mo | Hong Kong HK2 | $299.99 | $2999.99 | [Get this plan](https://bit.ly/BandwagonHost) |
| 320G HK CN2 GIA | 16 GB | 8x | 320 GB | 4000 GB/mo | Hong Kong HK2 | $589.99 | $5899.99 | [Get this plan](https://bit.ly/BandwagonHost) |
| 40G SG CN2 GIA | 2 GB | 2x | 40 GB | 500 GB/mo | Singapore SG1 | $49.99 | $499.99 | [Get this plan](https://bit.ly/BandwagonHost) |
| 80G SG CN2 GIA | 4 GB | 4x | 80 GB | 1000 GB/mo | Singapore SG1 | $86.99 | $869.99 | [Get this plan](https://bit.ly/BandwagonHost) |
| 160G SG CN2 GIA | 8 GB | 6x | 160 GB | 2000 GB/mo | Singapore SG1 | $165.99 | $1665.99 | [Get this plan](https://bit.ly/BandwagonHost) |
| 40G Tokyo CN2 GIA | 2 GB | 2x | 40 GB | 500 GB/mo | Tokyo TY8 | $89.99 | $899.99 | [Get this plan](https://bit.ly/BandwagonHost) |
| 80G Tokyo CN2 GIA | 4 GB | 4x | 80 GB | 1000 GB/mo | Tokyo TY8 | $155.99 | $1559.99 | [Get this plan](https://bit.ly/BandwagonHost) |

### ECommerce SLA VPS — Los Angeles (CN2 GIA-E)

This is the tier BandwagonHost itself recommends for China-facing workloads when Hong Kong/Japan prices feel steep. Los Angeles DC9 runs AMD EPYC nodes with NVMe RAID-10, dual redundant edge routers, and the best USA-to-China routing the company offers: CN2 GIA/CTGNet (AS4809/AS23764), China Unicom Premium (AS10099), China Mobile CMIN2 (AS58807), plus direct peering with Apple, Google, Meta, and ByteDance. The SLA bumps to **99.99%**, and the facility carries SOC 1/2, ISO 27001, PCI DSS, and HIPAA certifications — relevant if your WordPress site touches e-commerce or member data.

| Plan | RAM (ECC) | vCPU (AMD) | NVMe | Transfer | Link | Monthly | Annual | Buy |
|---|---|---|---|---|---|---|---|---|
| 20G ECommerce SLA | 1 GB | 2x | 20 GB | 1 TB/mo | 2.5 Gbps | — | $239.99 | [Get this plan](https://bit.ly/BandwagonHost) |
| 40G ECommerce SLA | 2 GB | 3x | 40 GB | 2 TB/mo | 2.5 Gbps | — | $399.99 | [Get this plan](https://bit.ly/BandwagonHost) |
| 80G ECommerce SLA | 4 GB | 4x | 80 GB | 3 TB/mo | 2.5 Gbps | $69.99 | $699.99 | [Get this plan](https://bit.ly/BandwagonHost) |
| 160G ECommerce SLA | 8 GB | 6x | 160 GB | 5 TB/mo | 5 Gbps | $109.99 | $1099.99 | [Get this plan](https://bit.ly/BandwagonHost) |

> A note on the buy links above: BandwagonHost's affiliate system supports deep-linking to a specific product via `&pid=PID`, but the per-plan PIDs are only visible by hovering each "Order Now" button on the live order page — they aren't published in a stable list. The links here route through the affiliate gateway to the main order page, where you select the exact plan and billing cycle. If you want to deep-link a specific plan for your own tracking, hover the Order Now button on [the official VPS page](https://bit.ly/BandwagonHost) and grab the `pid` value.

## Which Plan Fits Your WordPress Project

A pricing table is only useful if you know which row to look at. Here's how I'd map real WordPress scenarios onto BandwagonHost's lineup.

**A personal blog or a low-traffic portfolio site.** The **20G KVM PROMO at $49.99/year** is hard to argue with. 1 GB RAM is tight but workable for a single WordPress install with a lightweight theme and a small plugin set — install Nginx + PHP-FPM + MariaDB, turn on Opcache, add a free caching plugin like WP Super Cache or W3 Total Cache, and you'll serve a cached page in well under 200ms. The catch is no headroom: a viral post will exhaust that 1 GB and start swapping. If you can stretch to the **40G PROMO at $99.99/year**, the jump to 2 GB RAM and 3 vCPU is the single best value step in the whole lineup.

**A typical business site or small WooCommerce store.** The **80G KVM PROMO at $19.99/month** (4 GB RAM, 4 vCPU, 80 GB SSD, 3 TB transfer) is the sweet spot. WooCommerce with a couple of dozen products, a proper theme, and 6–10 plugins runs comfortably here, and you have room for Redis object caching without starving MariaDB. The 3 TB monthly transfer covers a lot of page views.

**A busy store, a membership site, or a multi-site install.** Step up to the **160G KVM PROMO at $39.99/month** (8 GB RAM, 5 vCPU). Once you're running a real store with daily backups, image processing, search plugins, and a staging copy, 8 GB stops feeling luxurious and starts feeling necessary.

**An audience in mainland China.** Don't pick the Basic PROMO tier — regular transit to China is brutal at peak hours. If budget is the priority, the **ECommerce SLA Los Angeles** tier at $239.99/year (20G) is the cheapest plan that rides CN2 GIA/CTGNet. If latency matters more than price — say you're running a China-facing membership site or a storefront where every 100ms counts — go straight to **Hong Kong CN2 GIA**, starting at $89.99/month for the 40G plan. The Hong Kong boxes cost roughly 4–6x the equivalent LA ECommerce plan, but they cut latency to Chinese telcos from ~150ms to ~30–40ms.

**A high-traffic content site or agency hosting multiple client sites.** The **320G ECommerce SLA** or the **320G/480G PROMO** tiers give you 16–24 GB RAM and the CPU cores to run several WordPress instances behind a single Nginx server block setup, with enough headroom for a staging environment per client.

## Network Choices and Why Location Matters for WordPress

WordPress performance is two problems stitched together: server-side speed (how fast PHP and MySQL produce the page) and network speed (how fast the finished bytes reach the reader). People obsess over the first and ignore the second. The second is often the bigger one.

BandwagonHost operates 19 datacenters. The ones that matter for most readers:

- **Los Angeles DC9** — the newest US node, AMD EPYC + NVMe, and the home of the CN2 GIA-E ECommerce tier. Best all-around choice if your audience spans the US and Asia.
- **New York** — also on EPYC + NVMe now. Lower latency for Europe and US East.
- **Hong Kong (HK2 / HK3 / HK8)** — the lowest-latency option for mainland China, on direct CN2 GIA. Physically locked in HK, no migration out.
- **Tokyo (TY8) and Osaka** — Japan CN2 GIA, slightly cheaper than Hong Kong, excellent for China + Japan audiences.
- **Singapore (SG1)** — the cheapest of the CN2 GIA family, good for Southeast Asia and southern China.
- **Vancouver** — the budget US-adjacent option on the Basic PROMO tier.

The practical move for a WordPress site: pick the datacenter closest to the median reader, and don't be afraid to migrate later — the Basic PROMO and ECommerce SLA tiers both support free panel-initiated migration between eligible datacenters, so you can start in LA and move to Hong Kong when your China traffic grows, without rebuilding the box.

## Recurring Promo Codes (the discount that keeps giving)

BandwagonHost's promo codes are a little unusual in a good way: they're **recurring**, meaning the discount applies on every renewal, not just the first invoice. That matters a lot for WordPress hosting, where you'll be paying for years.

Current publicly listed codes and their discount rates:

| Code | Discount | Type |
|---|---|---|
| `BWHCGLUKKB` | 6.77% | Recurring |
| `BWH34QMFYT2R` | 6.38% | Recurring |
| `BWH25AQH2CMQ` | 5.97% | Recurring |
| `ireallyreadtheterms8` | 5.5% | Recurring |
| `BWH2OJA9WE0O` | 5.39% | Recurring |

A 6% recurring discount sounds modest until you do the math on a $399.99/year plan renewed for five years — that's $120 saved for typing six characters at checkout. The codes are released as "easter eggs" and rotate periodically; the ones above are the publicly circulated set at time of writing. Apply the highest-percentage one that's still active at checkout.

To use one: pick a plan from [the BandwagonHost order page](https://bit.ly/BandwagonHost), proceed to checkout, and paste the code in the promo code field before paying.

## A Quick WordPress-on-BandwagonHost Setup Sketch

Because BandwagonHost is self-managed, here's the shape of what you'll do once your VPS is up. This isn't a full tutorial — there are plenty of those — but it's the map so you know what you're signing up for.

1. **Pick an OS template.** For WordPress today, Debian 13 or Ubuntu 26.04 are the sensible defaults. Both ship modern PHP and MariaDB.
2. **Install the stack.** Either go bare LEMP (`nginx` + `php8.3-fpm` + `mariadb-server` + `redis` + `certbot`) or install a free control panel for a GUI. **HestiaCP** and **CloudPanel** are both solid, free, and WordPress-friendly; **aaPanel** is popular with the Chinese-speaking user base.
3. **Harden the box.** SSH key auth, non-root sudo user, `ufw` firewall allowing only 22/80/443, fail2ban for SSH. KiwiVM also exposes a snapshot button — take one before you change anything big.
4. **Create the database and site.** `mysql -e "CREATE DATABASE wp..."`, download WordPress via WP-CLI or the tarball, point Nginx at the webroot, run `certbot --nginx` for free Let's Encrypt HTTPS.
5. **Wire up caching.** Opcache in PHP, Redis as an object cache backend (install the Redis Object Cache plugin), and either Nginx fastcgi cache or a page-cache plugin. This is where a VPS pulls ahead of shared hosting — you control the entire cache chain.
6. **Set up backups.** BandwagonHost gives you free automatic backups and snapshots at the VPS level; add a plugin-level backup (UpdraftPlus to an off-box S3-compatible bucket) so you have a copy outside the host.

Total time for a first-timer: an afternoon. For someone who's done it before: under an hour.

## Honest Tradeoffs to Know Before You Buy

No provider is right for everyone, and BandwagonHost has real tradeoffs you should walk in aware of.

**It's self-managed.** That's the big one. If you want a "WordPress just works" button, this isn't the provider. If you're willing to run `apt update`, it's one of the best value-for-money VPS hosts on the market.

**No cPanel by default.** KiwiVM handles VPS-level tasks (start/stop, OS reload, snapshots, rDNS, migration, usage stats) but it's not a website control panel. You'll add HestiaCP/CloudPanel/aaPanel yourself if you want one, or run the command line.

**The Basic PROMO tier uses SATA SSD, not NVMe.** Still RAID-10, still fine for most WordPress sites, but if you want the fastest database I/O, step up to the ECommerce SLA (NVMe) or the newer EPYC nodes in LA/HK/NY.

**CN2 GIA plans are not DDoS-tolerant.** BandwagonHost is explicit about this in its CN2 GIA documentation: the network has limited capacity, and under attack they null-route the IP rather than absorbing it. If you run a high-profile site that attracts DDoS, the Basic PROMO tier (on ChinaNet/163 transit) is actually more attack-tolerant, or you front the site with Cloudflare.

**Promo code discounts hover around 5–7%, not 50%.** Anyone advertising a "50% off BandwagonHost" code is either recycling an old one-shot promotion or being optimistic. The real, current, recurring discounts are in the 5.4–6.8% range. They stack up over years, but don't expect a halved bill.

## Final Checklist Before You Buy

If you came here looking for the best VPS for WordPress hosting, here's the decision in five lines:

- **Audience outside China, comfortable with the command line, budget-conscious** → 40G or 80G KVM PROMO.
- **Audience in China, budget-conscious** → 20G or 40G ECommerce SLA Los Angeles.
- **Audience in China, latency-critical** → Hong Kong CN2 GIA, 40G or 80G.
- **Running WooCommerce or a multi-site install** → 160G tier, PROMO or ECommerce SLA depending on audience.
- **Want the newest hardware and best routing** → ECommerce SLA Los Angeles (NVMe + CN2 GIA-E + 99.99% SLA).

Apply a recurring promo code at checkout, take a snapshot the moment the box is up, and you'll have a WordPress host that won't quit on you the next time a post goes mildly viral. The [BandwagonHost order page](https://bit.ly/BandwagonHost) lists every plan above with live pricing — pick the tier that matches your audience and traffic, and you're off.

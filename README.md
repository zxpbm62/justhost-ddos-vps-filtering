# Cheap DDoS Protected VPS: How Little Can You Pay, What Does the Filtering Actually Block, and Is a 12-Month Prepay Worth It? (Full JustHost Plan Table)

A DDoS-protected VPS starts at roughly **$2.25 a month** right now, and that number carries two conditions. You pay for 12 months in one go, and the filtering you get at that price handles network-layer floods, not HTTP floods. JustHost's entry plan, VPS Sirius, is 1 core, 1 GB RAM and 20 GB NVMe at $2.81/mo month-to-month, dropping to $2.25/mo on the annual term, with DDoS filtering listed as included on every plan in the range.

The rest of this page covers the full JustHost plan table, what "DDoS protected" means at this price level, how the industry's low-price mechanics work, and which plan is enough for a WordPress site, an API or a game server.

> **Quick pick**
> - **Most small sites, APIs and game servers:** VPS Vega, 2 cores, 4 GB RAM, 80 GB NVMe, **$7.79/mo**, or **$6.23/mo** on the 12-month term. It's the first plan with enough memory to run a control panel alongside a real workload.
> - **Sandbox, single static page, VPN or DNS node:** VPS Sirius at **$2.81/mo**.
> - Filtering is included on both. Neither price buys application-layer protection, so plan on your own WAF or rate limiting.
>
> 👉 [See JustHost's current VPS plans and 12-month prices](https://justhost.asia/en/vps?ref=196392)

## JustHost's full plan list

JustHost runs two parallel VPS lines. The "Special" line ships NVMe storage with an unmetered port, and the IPv4 + IPv6 line lets you pick HDD, SSD or NVMe at each size tier. Every price below is the monthly rate first and the 12-month rate second, since the annual discount is 20% across the entire list.

**Special offers, NVMe with unmetered port**

| Plan | CPU / RAM | NVMe | Port (fair-share) | Price monthly / 12-mo | Order |
| --- | --- | --- | --- | --- | --- |
| VPS Sirius | 1 core / 1 GB | 20 GB | 300 Mbit (93+ TB/mo) | $2.81 / $2.25 | [Select](https://justhost.asia/en/vps?ref=196392) |
| VPS Arcturus | 1 core / 2 GB | 30 GB | 300 Mbit (93+ TB/mo) | $4.01 / $3.21 | [Select](https://justhost.asia/en/vps?ref=196392) |
| VPS Vega | 2 cores / 4 GB | 80 GB | 500 Mbit (155+ TB/mo) | $7.79 / $6.23 | [Select](https://justhost.asia/en/vps?ref=196392) |
| VPS Yildun | 4 cores / 8 GB | 200 GB | 750 Mbit (232+ TB/mo) | $16.20 / $12.96 | [Select](https://justhost.asia/en/vps?ref=196392) |
| VPS Betelgeuse | 6 cores / 12 GB | 400 GB | 750 Mbit (232+ TB/mo) | $26.40 / $21.12 | [Select](https://justhost.asia/en/vps?ref=196392) |
| VPS Altair | 8 cores / 24 GB | 600 GB | 750 Mbit (232+ TB/mo) | $47.40 / $37.92 | [Select](https://justhost.asia/en/vps?ref=196392) |

**IPv4 + IPv6 line, choice of storage type**

| Plan | CPU / RAM | Disk | Price monthly / 12-mo | Order |
| --- | --- | --- | --- | --- |
| HDD VPS Start | 1 core / 512 MB | 5 GB HDD | $3.25 / $2.60 | [Select](https://justhost.asia/en/vps?ref=196392) |
| SSD VPS Start+ | 1 core / 512 MB | 5 GB SSD | $3.90 / $3.12 | [Select](https://justhost.asia/en/vps?ref=196392) |
| NVMe VPS Start++ | 1 core / 512 MB | 5 GB NVMe | $4.22 / $3.38 | [Select](https://justhost.asia/en/vps?ref=196392) |
| HDD VPS Standard | 2 cores / 2 GB | 25 GB HDD | $11.00 / $8.80 | [Select](https://justhost.asia/en/vps?ref=196392) |
| SSD VPS Standard+ | 2 cores / 2 GB | 25 GB SSD | $13.20 / $10.56 | [Select](https://justhost.asia/en/vps?ref=196392) |
| NVMe VPS Standard++ | 2 cores / 2 GB | 25 GB NVMe | $14.30 / $11.44 | [Select](https://justhost.asia/en/vps?ref=196392) |
| HDD VPS Super | 4 cores / 4 GB | 50 GB HDD | $22.00 / $17.60 | [Select](https://justhost.asia/en/vps?ref=196392) |
| SSD VPS Super+ | 4 cores / 4 GB | 50 GB SSD | $26.40 / $21.12 | [Select](https://justhost.asia/en/vps?ref=196392) |
| NVMe VPS Super++ | 4 cores / 4 GB | 50 GB NVMe | $28.60 / $22.88 | [Select](https://justhost.asia/en/vps?ref=196392) |

A third line sells IPv6-only KVM VPS with a choice of storage type, starting at **$1.60/mo**. There's also a plan constructor if none of the fixed configurations fit.

Everything else that affects a purchase decision, from the same pages:

- **DDoS filtering** ships with every plan. JustHost describes a multi-layered setup that monitors traffic and blocks attacks as they begin, aimed at "the main types" of DDoS.
- **45 server locations** and CN2 routes for faster access from mainland China, per the company description on its Trustpilot profile.
- Root access, free SSL, IPv4 + IPv6, a control panel and 24/7 support are listed as standard.
- **Vertical scaling** is available at any time: add cores, RAM or disk without migrating data to another machine.
- Billing is monthly or 12-month. No refund window is stated anywhere on the plan page, and no trial is mentioned.
- The plan pages publish no scrubbing capacity figure and make no claim about Layer 7 coverage. That gap matters for the next section.

👉 [Compare every JustHost VPS plan with the 12-month rate applied](https://justhost.asia/en/vps?ref=196392)

## What the filtering actually blocks at this price

"Protected" on a $2.79 plan and "protected" on a $499 plan are different products. Cloudzy's documentation is the clearest example of where the line sits: its included mitigation absorbs volumetric floods (UDP flood, SYN flood, ICMP flood, DNS amplification, NTP reflection), and the page states outright that application-layer attacks need "additional tools like rate limiting or WAF, which you configure on your server." That's Layer 3 and Layer 4 only, on every tier including the $2.48 one.

Rad Web Hosting splits the two in a side-by-side table. Standard protection caps at 5 Gbps, covers Layer 3 and 4, and has no Layer 7 coverage. Premium goes to "1+ Tbps" with an advanced WAF, bot detection and custom traffic rules. Liquid Web draws the same line with prices attached: the free tier handles volumetric attacks up to 2 Gbps, Advanced costs $99/mo per server for up to 10 Gbps, and Premium runs $499/mo per account for what the page calls complete protection.

JustHost sits in the first category by description. Its pages promise filtering of traffic floods and say nothing about HTTP floods, WAF rules or scrubbing capacity. Treat the included protection as absorbing network-layer floods, and assume you still need to handle Layer 7 yourself: a reverse proxy, rate limits in nginx, fail2ban, Cloudflare in front of the site. That work is the same whether you pay $2.25 or $17, and it's the part most "DDoS protected" headlines skip.

## Where the low price comes from

Three mechanisms produce the sub-$3 numbers you see across this market, and they're not equivalent.

**Annual or multi-year prepay.** JustHost takes 20% off for a 12-month commitment. VPS Vega costs $7.79 monthly or $6.23 prepaid, a $18.72 saving over the year and a real one, since the monthly price stays available if you'd rather keep the exit open. Rad Web Hosting goes much further: its $15.96 DDOS-SSD-1 entry plan is flagged on the page as a 36-month term price, against a $39.99 monthly rate. That's roughly $574.56 committed before you've run a single request.

**Promotional discounts with no published renewal price.** Cloudzy's $2.48 headline is $4.95 marked 50% off, and the page never says what the plan costs when the promotion ends. A discount with no end date is a price you can't budget for.

**Paid protection tiers.** Liquid Web's free filtering stops at 2 Gbps and its $99/mo add-on does the rest. Rad's Layer 7 WAF lives in the Premium column. If your threat model includes HTTP floods, the cheap tier isn't the finished product.

Entry pricing across the market, for scale:

| Provider | Cheapest protected plan | Price | Term notes |
| --- | --- | --- | --- |
| JustHost | VPS Sirius, 1 core / 1 GB / 20 GB NVMe | $2.81/mo, $2.25/mo on 12 months | 20% annual discount |
| Cloudzy | 512 MB / 1 vCPU / 20 GB NVMe | $2.48/mo, listed as 50% off $4.95 | renewal price not published |
| LightNode | 2 GB / 1 vCPU / 50 GB NVMe | $7.71/mo | hourly billing |
| BlastVPS | 4 GB / 2 vCore / 40 GB NVMe | $10.99/mo | unlimited bandwidth, L3/L4 mitigation |
| Rad Web Hosting | 1 GB / 16 GB SSD / 1 TB | $15.96/mo | requires 36-month term, $39.99 monthly |
| Liquid Web | 4 GB / 1 vCPU / 120 GB | $17/mo | free tier covers up to 2 Gbps |

The useful habit: multiply the advertised monthly rate by the number of months you must commit, then add whatever the Layer 7 tooling will cost you. On a 36-month contract the cheapest-looking plan in that table is the most expensive one.

👉 [Lock in the $6.23 rate on VPS Vega with a 12-month term](https://justhost.asia/en/vps?ref=196392)

## Which plan fits which job

**512 MB to 1 GB (Start tiers, VPS Sirius).** Enough for a static site, a WireGuard endpoint, an authoritative DNS node, a monitoring agent or a staging box. Not enough for WordPress with a page builder and a caching plugin, not enough for Windows, not enough for a Minecraft server with mods. If the plan needs a control panel, skip this tier.

**2 GB (VPS Arcturus, Standard tiers).** The floor for a small WordPress site with a database on the same machine, a lightweight API, or a TeamSpeak/Mumble voice server. Expect to tune MySQL and PHP-FPM rather than run defaults.

**4 GB (VPS Vega).** The practical starting point for production: a WordPress site with real traffic, a Docker host running three or four containers, a small game server, a CI runner. Two cores at this size handle a control panel and an app without swapping.

**8 GB and up (VPS Yildun through Altair).** Modded game servers, in-memory caches, multiple databases, anything running JVM workloads. The 24 GB Altair at $37.92/mo prepaid is the cheapest route to a large single instance in this lineup.

**Game servers and voice servers** care about two things beyond RAM: location and UDP handling. JustHost lists 45 locations including CN2 routes, so pick a region close to your players. On the filtering side, the plan pages make no specific claim about game protocol filtering, so ask support which UDP-heavy traffic their filters treat as legitimate before you buy for a CS2 or Valheim server.

**Anything facing HTTP floods** needs a WAF in front. Budget for Cloudflare's free tier or a similar proxy, or a ruleset on the server. That's true at every price point in this article.

## What reviewers report

The Trustpilot profile for justhost.asia carries a mixed picture, and the negative reviews are specific enough to plan around. One reviewer describes a support chat that failed to recognize the account's own IP address until a screenshot was produced, followed by a full outage on 2 March 2026 with no status updates for 15 hours. Another reports a VPS down for more than a day and moving regions after speeds collapsed to around 20 Mbit/s with 1500 ms ping. A third reports tickets answered only after the server came back up. The company-written blurb at the top of the same page advertises the 45 locations, NVMe storage, unlimited traffic, free SSL, DDoS protection, root access and CN2 connectivity.

Those complaints point to a pattern worth pricing in: this is an unmanaged budget host where the value is in the resource-per-dollar ratio, and the risk sits in support responsiveness and uptime during incidents. Backups stored somewhere else, a second VPS as failover, and a status check before you commit anything revenue-critical. A cheap protected VPS is a good place to run a side project, a game community or a low-traffic API. It's a bad place to be the only copy of anything.

👉 [Start on the monthly VPS Sirius plan and test it for one billing cycle](https://justhost.asia/en/vps?ref=196392)

## FAQ

**How large an attack will the cheapest JustHost plan survive?**
The pages don't publish a mitigation capacity, so there's no number to quote. For reference, providers that do publish figures put free-tier volumetric protection at 2 Gbps (Liquid Web) and sell 10 Gbps or "1+ Tbps" as paid upgrades (Liquid Web, Rad Web Hosting). Ask JustHost support directly if you expect attacks above a few Gbps.

**Does DDoS protection cost extra on JustHost?**
No. Filtering is listed as included on every plan, from the $2.25 VPS Sirius up to VPS Altair. What isn't included, at this or any comparable price, is application-layer protection.

**Can I get a refund if it doesn't work out?**
No money-back period is stated on the plan pages or the order flow I could see. Confirm the refund terms with support before you prepay 12 months.

**Do I need to configure a firewall myself?**
For anything above network-layer floods, yes. iptables, nftables, fail2ban, a WAF or a filtering CDN in front of the site. On comparable hosts, the same is true: Rad Web Hosting ships no port blocks and recommends installing CSF yourself.

**Can I upgrade later without reinstalling?**
JustHost says you can add CPU cores, RAM or disk at any time, with changes applied quickly and minimal downtime. That makes starting small on VPS Sirius and scaling to Vega a viable path if you'd rather not prepay a bigger plan up front.

## Before you order

Match the plan to the workload first. 512 MB to 1 GB for sandboxes, DNS, VPN and static pages; 2 GB for a small WordPress site or voice server; 4 GB (VPS Vega) for anything you'd call production; 8 GB and above for modded game servers and multi-service hosts.

Then confirm two things that no table can settle for you. Whether the 12-month term is worth the commitment given that no refund window is published, and whether the included filtering covers the attack type you actually expect. If your problem is HTTP floods and credential stuffing, budget for a WAF on top before you compare monthly rates at all.

👉 [Pick your JustHost plan and check the current 12-month pricing](https://justhost.asia/en/vps?ref=196392)

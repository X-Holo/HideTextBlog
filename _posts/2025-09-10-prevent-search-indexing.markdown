---
layout: post
title:  "Invisible Links: Using noindex and Canonical Tags to Shield Privacy"
date:   2026-07-20 23:40:00 +0800
categories: seo privacy
---

## Preventing Search Engine Indexing
URLs can carry sensitive data. HideText uses two simple, practical measures so those links don't become searchable.

1) HTTP-level noindex

- When a URL contains a ciphertext parameter (`?c=`), the server adds `X-Robots-Tag: noindex, nofollow` to the response header.  
- This tells crawlers not to index the URL before they parse the page, which is more reliable for parameterized links than an HTML meta tag.

2) Canonical pointing

- Each ciphertext page includes a `<link rel="canonical" href="https://hide-text.com/">`.  
- Crawlers are instructed to treat the encrypted URL as part of the main site, preventing separate indexing or ranking for each random link.

Verification

- We verify this behavior empirically — a page can be indexed while its HideText links remain unsearchable. See the test details: {% post_url 2025-09-10-verification-test %}.

For a simple explanation of how the data is transformed before these layers, see: {% post_url 2025-09-10-XOR-base64 %}.
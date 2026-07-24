---
layout: post
title:  "Preventing Search Engine Indexing"
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

### Summary

- **Random links are not indexed:** URLs containing ciphertext parameters (for example `?c=...`) are prevented from being indexed and should not appear in search results.
- **The domain is indexed:** The root site (`https://hide-text.com/`) remains indexable and will be treated normally by search engines.
- **Practical effect:** You can create many random-looking links that reveal the same content without creating searchable traces.


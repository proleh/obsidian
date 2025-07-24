---
creation date: 24-07-2025
modification date: Thursday 24th July 2025 16:40:19
---
Rel:
Tags: #performance #cashe #browser

There are next cache directives:
1. no-cache - validates caches response with the serve before using it.
2. must-revalidate - revalidated stale response with the server before using it.
3. no-store - doesn't cache any part of the response or request
4. private - prevents caching on shared caches(CDN, proxies), allows only browser cache.
5. stale-while-revalidated - serves stale content while validating the cached response with the server.
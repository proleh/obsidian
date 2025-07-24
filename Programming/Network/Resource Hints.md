---
creation date: 23-07-2025
modification date: Wednesday 23rd July 2025 21:07:07
---
Rel:
Tags:  #network


There are for resource hints that can be used to improve performance:
1. dns-prefetch - performs domain name resolution in the background(Through [[DNS Resolver]]).
2. preconnect - dns-prefetch + TCP\TLS handshake
3. prefetch - downloads a resource ahead of time even if they're immediately needed.
4. preload - downloads the resource.
5. prerender: - load a full hidden page in the background

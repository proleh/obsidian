When the domain was entered in the url browser not magically knows to which server it needs to connect.
First step is to check the cache if there is already record that matches this domain and to get IP. If there is no IP or it's stale(cache expired):
1. Browser sends request to Recursive DNS resolver.
2. DNS resolver  -> Root Name Server(the one which knows all IPs for .com, .ua, .uk etc).
3. Root Name Server replies with the IP of Top Level Domain(TLD) IP address.
4. DNS Resolver -> TLD.
5. TLD replies with Authoritative Domain Server IP.
6. DNS Resolver -> Authoritative Domain Server
7. Authoritative replies with website's IP.
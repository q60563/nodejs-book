# Table of Contents

- DNS
  - dns.getServers()
  - dns.lookup(hostname[, options], callback)
    - Supported getaddrinfo flags
  - dns.lookupService(address, port, callback)
  - dns.resolve(hostname[, rrtype], callback)
  - dns.resolve4(hostname, callback)
  - dns.resolve6(hostname, callback)
  - dns.resolveCname(hostname, callback)
  - dns.resolveMx(hostname, callback)
  - dns.resolveNs(hostname, callback)
  - dns.resolveSoa(hostname, callback)
  - dns.resolveSrv(hostname, callback)
  - dns.resolvePtr(hostname, callback)
  - dns.resolveTxt(hostname, callback)
  - dns.reverse(ip, callback)
  - dns.setServers(servers)
  - Error codes
  - Implementation considerations
    - dns.lookup()
    - dns.resolve(), dns.resolve*() and dns.reverse()



# DNS
# dns.getServers()
# dns.lookup(hostname[, options], callback)
### Supported getaddrinfo flags
# dns.lookupService(address, port, callback)
# dns.resolve(hostname[, rrtype], callback)
# dns.resolve4(hostname, callback)
# dns.resolve6(hostname, callback)
# dns.resolveCname(hostname, callback)
# dns.resolveMx(hostname, callback)
# dns.resolveNs(hostname, callback)
# dns.resolveSoa(hostname, callback)
# dns.resolveSrv(hostname, callback)
# dns.resolvePtr(hostname, callback)
# dns.resolveTxt(hostname, callback)
# dns.reverse(ip, callback)
# dns.setServers(servers)
# Error codes
# Implementation considerations
### dns.lookup()
### dns.resolve(), dns.resolve*() and dns.reverse()
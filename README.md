# NicTool

NicTool is a free DNS management suite that takes the headaches out of managing
DNS data. NicTool works great for managing one zone or millions of them. It
works well with one nameserver or dozens of them.

NicTool is not a DNS server. NicTool exports sanitized and validated DNS data
to authoritative DNS servers such as tinydns, BIND, PowerDNS, NSD, and MaraDNS.

NicTool is Open Source, you can fork it on GitHub:
https://github.com/msimerson/NicTool

NicTool includes:

- an attractive web interface for users, admins, and clients
- validation of all DNS data before acceptance
- fine grained permissions for users and groups
- delegatation of zones and zone records to users and/or groups.
- logging of all DNS changes (who did what & when)
- RDBMS data storage
- a mature API for automation and integration

NicToolServer is the server component of NicTool. It connects to the database
where the DNS information resides. All changes to DNS data (zones, records,
nameservers) and managers (users and groups) is validated by NicToolServer
before insertion.

NicToolServer functions as a web service. It provides a SOAP or RPC-XML server
for applications. The format of requests is defined in the reference API at
http://www.nictool.com/docs/api/. The API and NicToolClient both connect to
NicToolServer via this web service.

NicToolClient is a CGI application. It is what you see in the browser. It
provides a web interface for managing DNS data. NicToolClient has customizable
HTML templates and a CSS style sheet.

The NicTool API is a mature and full featured API for connecting to
NicToolServer and managing DNS data. There are many scripts written against
this API and it is stable.

Usage Examples:
- ColocateUSA.net (2012-): Custom scripts for web services (billing, orders,
  CP) to set & reset rDNS, and CLI scripts to update forward and rDNS for
- Spry/VPSlink (2007-2010): We wrote Control Panels that allowed clients to
  manage virtual machines. We provided a custom DNS manager so our clients
  could manage their domains and the rDNS for their IPs, supported by the
- Layered Tech (2005-2007): DNS management was limited to internal staff and
  was updated as needed. Which meant, lots of old poorly maintained data. I
  wrote a number of scripts for common tasks like "reset the rDNS for these
- Lightrealm/HostPro/Interland/Web.com (2000-2003): In 1999, Lightrealm's DNS
  was managed on Sun servers running BIND 4. DNS team members used a shared
  login for access and editing of the zone and named.conf files. We had
  120,000 zones and reloading BIND took about 12 hours, so it was done once a
  day. If someone made an error, it might take 10 hours before BIND
  encountered it and croaked, sometimes extending the time-to-publish of DNS
  data to days.  With the pending merger of Lightrealm, Vservers, and
  HostPro, our zone count was going to almost triple. We needed a better
  solution and found NicTool. We deployed a system that elegantly managed
  400,000 zones, millions of zone records, and published changes in under a
  minute. NicTool remained in use at Web.com for many years thereafter.

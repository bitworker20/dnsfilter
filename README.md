# Simple DNS filter

Fork from osesov/dnsfilter

- forward requests to upstream server and post-process results
- Resolve name to ipv4/ipv6 from local database (in addition to forwarded results)
- Filter IPv4 or IPv6 addresses from results.
- bind to interface

new features:
- add per domain ipv4/ipv6 filter, for example:

    ```s
    $ sudo dnsfilter --pdc google.com:4 youtube.com:6 google.de:6
    ```
    _(google.com:4 meaning only ipv4 will return when query google.com etc.)_

- More debug information like ipv6 addr, colorful output.


# systemd

copy provided dnsfilter@.service to /etc/systemd/system/dnsfilter@.service and edit as appripriate.
then

    $ systemctl start dnsfilter@<IP-OR-INTERFACE-NAME>.service

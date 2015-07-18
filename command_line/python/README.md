# PassiveTotal Command Line Interface

PassiveTotal CLI uses the docopts library which is self documenting. For usage, simple run the tool without any switches and you will see the available commands. By default, output is formatted for easy viewing, but if desired the raw JSON response can be specified.

# Usage

<pre>
passivetotal_cli.py metadata <indicator> [--raw]
passivetotal_cli.py passive <indicator> [--raw]
passivetotal_cli.py subdomains <indicator> [--raw]
passivetotal_cli.py unique <indicator> [--raw]
passivetotal_cli.py classify <indicator> (targeted|crime|multiple|benign) [--bulk]
passivetotal_cli.py (add|remove) tag <indicator> <tag> [--bulk]
passivetotal_cli.py (-h | --help)
passivetotal_cli.py --version
</pre>

# Sample Output

## Metadata

<pre>
[=] Query: 104.131.121.205
[*] Country: N/A
[*] Network: 104.131.64.0/18
[*] AS Number: 393406
[*] AS Name: DIGITALOCEAN-ASN-NY3 - Digital Ocean
[*] Sinkhole?: False
[*] Ever Compromised?: False
[*] Tags: digital_ocean
</pre>

## Passive DNS

<pre>
[=] Query: passivetotal.org
[*] First Seen: 2014-04-15 00:00:00
[*] Last Seen: 2015-07-09 19:37:36
[*] Resolve Count:  4
[*] Resolutions
=> 104.131.121.205      2014-10-27 00:00:00     2015-07-09 19:37:36     mnemonic, ntotal, pingly, domaintools, kaspersky
=> 107.170.89.121       2014-05-22 03:44:14     2015-06-02 01:25:48     mnemonic, ntotal, pingly, domaintools, kaspersky
=> 162.243.102.221      2014-04-16 00:00:00     2014-10-20 01:17:56     ntotal, domaintools
=> 107.170.89.121       2014-04-15 00:00:00     2014-08-14 00:00:00     virustotal, domaintools
</pre>

## Subdomains

<pre>
[=] Query: *.passivetotal.org
[*] First Seen: 2014-05-08 00:00:00
[*] Last Seen: 2015-07-09 20:24:08
[*] Subdomains:  www
[=] www Resolutions
=> 104.131.121.205      2015-06-02 08:54:22     2015-07-09 18:22:27     mnemonic, dnsres, pingly
=> 107.170.89.121       2014-12-25 04:32:29     2015-06-02 00:22:03     dnsres, pingly
=> 104.131.121.205      2015-06-02 00:00:00     2015-06-02 00:00:00     virustotal
=> 107.170.89.121       2014-05-08 00:00:00     2015-06-01 23:50:29     mnemonic, pingly, dnsres, virustotal, kaspersky
</pre>

## Unique

<pre>
[=] Query: passivetotal.org
[*] Resolutions
=> 107.170.89.121       [2]
=> 104.131.121.205      [1]
=> 162.243.102.221      [1]
</pre>

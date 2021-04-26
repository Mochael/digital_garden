---
title: Tor Network and .Onion Domains
tree_state: 🌱
---

### Tor vs "Private" or "Incognito" Mode
While the names may imply otherwise, 'Incognito mode' and 'private tabs' do not make you anonymous on the Internet. They erase all the information on your machine relating to the browsing session after they are closed, but have no measures in place to hide your activity or digital fingerprint online. This means that an observer can collect your traffic just as easily as any regular browser.

Tor Browser offers all the amnesic features of private tabs while also hiding the source IP, browsing habits and details about a device that can be used to fingerprint activity across the web, allowing for a truly private browsing session that's fully obfuscated from end-to-end.


### What is .Onion Domain
Even though .onion addresses are not actual DNS names, some apps/web browsers can access sites with .onion addresses (like poop123.onion) by sending the request through the Tor network.

### How does Tor Work
Read about it here: https://en.wikipedia.org/wiki/Tor_%28anonymity_network%29. But it sounds like it's a protocol where for example:
1. a user requests info from a page (could also post info to a page or do anything)
2. the request passes through a network of computers, where each computer only receives a portion of the information from the request. They only know the information about where to send the request next.
3. then after passing through all the computers they send the user back the info from the webpage without ever having seen the user's IP address
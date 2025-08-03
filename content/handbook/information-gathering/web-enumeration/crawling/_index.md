---
title: Crawling
type: handbook
weight: 4
---
---

### Cheat sheet

* Check for /robots.txt

| URI Suffix                        | Description                                                                                      | Status      | Reference                                                                                      |
|----------------------------------|--------------------------------------------------------------------------------------------------|-------------|------------------------------------------------------------------------------------------------|
| `security.txt`                   | Contains contact info for security researchers to report vulnerabilities.                       | Permanent   | [RFC 9116](https://www.rfc-editor.org/rfc/rfc9116.html)                                       |
| `/.well-known/change-password`   | Standard URL to direct users to a password change page.                                          | Provisional | [W3C Draft](https://w3c.github.io/webappsec-change-password-url/#the-change-password-well-known-uri) |
| `openid-configuration`           | Provides config details for OpenID Connect over OAuth 2.0.                                       | Permanent   | [Spec](http://openid.net/specs/openid-connect-discovery-1_0.html)                             |
| `assetlinks.json`                | Verifies ownership of digital assets (like apps) tied to a domain.                              | Permanent   | [Spec](https://github.com/google/digitalassetlinks/blob/master/well-known/specification.md)   |
| `mta-sts.txt`                    | Defines SMTP MTA Strict Transport Security policy to secure email delivery.                     | Permanent   | [RFC 8461](https://www.rfc-editor.org/rfc/rfc8461.html)                                       |


#### ReconSpider

```
pip3 install scrapy --break-system-packages
wget -O ReconSpider.zip https://academy.hackthebox.com/storage/modules/144/ReconSpider.v1.2.zip
unzip ReconSpider.zip

python3 ReconSpider.py http://inlanefreight.com
```

**Crawling**, often called spidering, is the automated process of systematically browsing the World Wide Web. 



---
title: Fingerprinting
type: handbook
weight: 3
---
---

### Banner Grabbing


| Commands                  | Description     |
|---------------------------|-----------------|
| curl -I inlanefreight.com | Banner Grabbing |

### Whatweb


| Commands         | Description   |
|------------------|---------------|
| whatweb <domain> | Whatweb Usage |

### Wafw00f

`pip3 install git+https://github.com/EnableSecurity/wafw00f`
   

| Commands         | Description   |
|------------------|---------------|
| wafw00f <domain> | Wafw00f Usage |

### Nikto

```
sudo apt update && sudo apt install -y perl
git clone https://github.com/sullo/nikto
cd nikto/program
chmod +x ./nikto.pl
```

| Commands                             | Description |
|--------------------------------------|-------------|
| `nikto -h inlanefreight.com -Tuning b` | Nikto Usage |


 



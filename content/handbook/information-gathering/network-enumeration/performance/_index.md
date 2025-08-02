---
title: Performance
type: handbook
prev: handbook/performance/
weight: 5
---
---

### Timeouts

#### Round-Trip-Time (RTT)

`sudo nmap <subnet> -F --initial-rtt-timeout 50ms --max-rtt-timeout 100ms`

### Max Retries

`sudo nmap <subnet> -F --max-retries 0 | grep "/tcp" | wc -l`

### Rates

`sudo nmap <subnet> -F -oN tnet.minrate300 --min-rate 300`

### Timing

```• -T 0 / -T paranoid
• -T 1 / -T sneaky
• -T 2 / -T polite
• -T 3 / -T normal
• -T 4 / -T aggressive
• -T 5 / -T insane
```

`sudo nmap 10.129.2.0/24 -F -oN tnet.T5 -T 5`



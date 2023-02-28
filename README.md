# passivedns
Containerized PassiveDNS

## Run
```docker compose up --remove-orphans```

## Output 

Sample Output of docker compose 

```
[+] Running 2/2
Attaching to noisy, passivedns
noisy       | WARNING:root:Error connecting to root url: https://www.woostercollective.com
noisy       | INFO:root:Visiting https://www.dotdashmeredith.com
noisy       | INFO:root:Visiting https://www.dotdashmeredith.com/_nuxt/a61d0e5.js

passivedns  | 1677623228.112756||10.1.1.1||8.8.8.8||IN||www.dotdashmeredith.com.||CNAME||www.dotdash.com.||569||1
passivedns  | 1677623228.112756||10.1.1.1||8.8.8.8||IN||www.dotdash.com.||CNAME||k.sni.global.fastly.net.||569||1
passivedns  | 1677623228.112756||10.1.1.1||8.8.8.8||IN||k.sni.global.fastly.net.||A||199.232.190.137||5||1

noisy       | INFO:root:Visiting https://longreads.com/about/
passivedns  | 1677623717.876145||10.1.1.1||8.8.8.8||IN||www.longreads.com.||CNAME||longreads.com.||60||1
passivedns  | 1677623717.876145||10.1.1.1||8.8.8.8||IN||longreads.com.||A||192.0.79.32||300||1
passivedns  | 1677623717.876145||10.1.1.1||8.8.8.8||IN||longreads.com.||A||192.0.79.33||300||1
passivedns  | 1677623718.038105||10.1.1.1||8.8.8.8||IN||longreads.com.||A||192.0.79.32||300||1
passivedns  | 1677623718.038105||10.1.1.1||8.8.8.8||IN||longreads.com.||A||192.0.79.33||300||1
passivedns  | 1677623718.220300||10.1.1.1||8.8.8.8||IN||longreads.com.||A||192.0.79.32||300||1
passivedns  | 1677623718.220300||10.1.1.1||8.8.8.8||IN||longreads.com.||A||192.0.79.33||300||1
noisy       | INFO:root:Visiting https://longreads.com/wp-json/oembed/1.0/embed?url=https%3A%2F%2Flongreads.com%2Fabout%2F&#038;format=xml
passivedns  | 1677623729.547751||10.1.1.1||8.8.8.8||IN||longreads.com.||A||192.0.79.32||300||1
```

## Pipe delimited output
```
#timestamp||dns-client ||dns-server||RR class||Query||Query Type||Answer||TTL||Count
1322849924.408856||10.1.1.1||8.8.8.8||IN||upload.youtube.com.||A||74.125.43.117||46587||5
1322849924.408857||10.1.1.1||8.8.8.8||IN||upload.youtube.com.||A||74.125.43.116||420509||5
1322849924.408858||10.1.1.1||8.8.8.8||IN||www.adobe.com.||CNAME||www.wip4.adobe.com.||43200||8
1322849924.408859||10.1.1.1||8.8.8.8||IN||www.adobe.com.||A||193.104.215.61||43200||8
1322849924.408860||10.1.1.1||8.8.8.8||IN||i1.ytimg.com.||CNAME||ytimg.l.google.com.||43200||3
1322849924.408861||10.1.1.1||8.8.8.8||IN||clients1.google.com.||A||173.194.32.3||43200||2
```

## JSON output
```
{"timestamp_s":1677622871,"timestamp_ms":756570,"client":"10.1.1.1","server":"8.8.8.85","class":"IN","query":"www.digitaltrends.com.","type":"A","answer":"192.0.66.16","ttl":31340,"count":1}
{"timestamp_s":1677622871,"timestamp_ms":937444,"client":"10.1.1.1","server":"8.8.8.8","class":"IN","query":"www.digitaltrends.com.","type":"A","answer":"192.0.66.16","ttl":31340,"count":1}
{"timestamp_s":1677622883,"timestamp_ms":313351,"client":"10.1.1.1","server":"8.8.8.8","class":"IN","query":"downloads.digitaltrends.com.","type":"CNAME","answer":"downloads-site.dgtcdn.net.","ttl":3600,"count":1}
{"timestamp_s":1677622883,"timestamp_ms":313351,"client":"10.1.1.1","server":"8.8.8.8","class":"IN","query":"downloads-site.dgtcdn.net.","type":"A","answer":"35.227.210.81","ttl":600,"count":1}
{"timestamp_s":1677622927,"timestamp_ms":503175,"client":"10.1.1.1","server":"8.8.8.8","class":"IN","query":"www.digitaltrends.com.","type":"A","answer":"192.0.66.16","ttl":31340,"count":1}
```

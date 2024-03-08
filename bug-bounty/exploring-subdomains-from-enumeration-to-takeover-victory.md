# Exploring Subdomains: From Enumeration to Takeover Victory

In the name of ALLAH the most gracious the most merciful

So today i will talk about how i got my critical subdomain takeover on ford motors&#x20;

> _Ford_ is a family _company_, one that spans the globe and has shared ideals. We value service to each other and the world as much as to our customers. Generations ...

### Choose target

<figure><img src="../.gitbook/assets/image (26).png" alt=""><figcaption><p>our target is ford.com domain</p></figcaption></figure>

### Subdomain enumeration

First i collected subdomains using subMonit88r

```bash
# Tool link: https://github.com/h0tak88r/submonit88r
go install github.com/h0tak88r/subMonit88r@latest

# Usage
subMonit88r -l domains.txt
# Results saved to subMonit88rResults.txt
```

<figure><img src="../.gitbook/assets/image (20).png" alt=""><figcaption></figcaption></figure>

### Subdomain Takeover checking

So here i used my another go tool subov88r&#x20;

```bash
# Tool Link 
https://github.com/h0tak88r/subov88r
# Install
go install github.com/h0tak88r/subov88r@latest
# passing submonit88r results to subov88r
subov88r -f subMonit88rResults.txt
```

The results was something like&#x20;

<figure><img src="../.gitbook/assets/image (22).png" alt=""><figcaption></figcaption></figure>

the result that talk my attention was like&#x20;

```bash
Subdomain: www.<subdomain>.ford.com ,  CNAME: <subdomain>.trafficmanager.com, Status: NXDOMAIN
```

So i quickly started to look into this subdomain but the `httpx` tool didn't recognize this subdomain aas a valid domain&#x20;

Then i decided to see this subdomain in the browser and as i expected\


<figure><img src="../.gitbook/assets/image (38).png" alt=""><figcaption><p>Message that the subdomain may not be valid</p></figcaption></figure>

Ok let's check can i take over xyz project&#x20;

[https://github.com/EdOverflow/can-i-take-over-xyz/issues/35](https://github.com/EdOverflow/can-i-take-over-xyz/issues/35)\
Oh no they say that it is not vulnerable&#x20;

<figure><img src="../.gitbook/assets/image (23).png" alt=""><figcaption></figcaption></figure>

Still, I didn't give up. I decided to investigate on my own, and guess what? I found out that there was indeed an issue, and I successfully took control of it. It's always good to double-check! 🛡️🌐

Undeterred, I decided to manually investigate, and voila! Success – I managed to take over the CNAME `<vulnerable>.trafficmanager.com` . Always good to verify! 🛡️🌐

<figure><img src="../.gitbook/assets/image (24).png" alt=""><figcaption></figcaption></figure>

Then reported the issue woth HIGHT severity and the Team changed the severity to Critical and triaged my report \


<figure><img src="../.gitbook/assets/image (25).png" alt=""><figcaption></figcaption></figure>
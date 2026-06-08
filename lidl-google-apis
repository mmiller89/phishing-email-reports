# Phishing Email Analysis – Lidl Prize Giveaway Campaign

## Disclaimer

All indicators of compromise (IOCs) contained in this report have been intentionally **defanged** to prevent accidental interaction with potentially malicious infrastructure.

---

# Email Artifacts

| Artifact          | Value                                                        |
| ----------------- | ------------------------------------------------------------ |
| Sender            | `noreply[@]sroilknb[.]0il7wqyd[.]com`                        |
| Reply-To          | `redacted[@]myemail[.]com`                                   |
| Date              | `Fri, 15 May 2026 19:26:07`                                  |
| Sending Server IP | `94[.]130[.]230[.]238`                                       |
| Reverse DNS       | `static[.]238[.]230[.]130[.]94[.]clients[.]your-server[.]de` |
| Recipient         | `redacted[@]myemail[.]com`                                   |
| Subject           | `redacted ¡No dejes pasar esta increíble oportunidad!`       |

---

## Embedded URL

```text
hxxps://storage[.]googleapis[.]com/xhr09fe05fe2026/optimisticdigital[.]xyz[.]html#4QLEzM115869yPdp1460prrsgaotla2139RKCREJWERIZNBDQ242763VOED180491R21
```

---

# Email Description

This email is a classic "You've won a prize" phishing campaign that uses Lidl brand impersonation to encourage recipients to click a malicious link.

The email claims that the recipient has been selected to receive a free Makita tool set and attempts to create urgency through promotional language and prize-themed social engineering.

The embedded URL initially appears trustworthy because it utilizes Google's cloud infrastructure (`storage[.]googleapis[.]com`) rather than a clearly suspicious domain.

---

# Malicious Artifact Analysis

## URL Analysis

### Observed URL

```text
hxxps://storage[.]googleapis[.]com/xhr09fe05fe2026/optimisticdigital[.]xyz[.]html
```

Dynamic analysis revealed that the Google Cloud Storage URL redirected users toward phishing infrastructure hosted on:

```text
optimistic-digital[.]xyz
```

ANY.RUN classified the activity as:

* Possible Phishing
* Evil Redirect
* Phishing

The sandbox generated an overall verdict of **Malicious Activity**.

### Redirect Behavior

Observed redirect chain:

```text
hxxps://storage[.]googleapis[.]com/xhr09fe05fe2026/optimisticdigital[.]xyz[.]html
        ↓
optimistic-digital[.]xyz
        ↓
HTTP 301 Redirect
```

This indicates that Google Cloud Storage was being used as an intermediary redirector to improve legitimacy and potentially evade filtering controls.

---

## WHOIS Analysis

The SMTP envelope sender (Return-Path) utilized:

```text
dfg55fg5dfgfg[.]emprendedesde[.]us[.]com
```

The parent domain:

```text
emprendedesde[.]us[.]com
```

was registered approximately **10 days prior** to receipt of the phishing email.

Additional observations:

* WHOIS privacy enabled
* Cloudflare nameservers observed
* Recently registered domain
* Consistent with infrastructure commonly observed in phishing campaigns

Newly registered domains frequently have limited reputation history and are often used in short-lived phishing campaigns.

---

## Infrastructure Analysis

### Sending Infrastructure

| Indicator   | Value                                                        |
| ----------- | ------------------------------------------------------------ |
| Sending IP  | `94[.]130[.]230[.]238`                                       |
| Reverse DNS | `static[.]238[.]230[.]130[.]94[.]clients[.]your-server[.]de` |
| ASN         | `AS24940`                                                    |
| Provider    | `Hetzner Online GmbH`                                        |

The email originated from infrastructure hosted by Hetzner, a legitimate German cloud and hosting provider.

### Redirect Infrastructure

Dynamic analysis observed DNS resolution for:

```text
optimistic-digital[.]xyz
```

which resolved to:

```text
185[.]80[.]129[.]75
```

The sandbox subsequently observed HTTP redirection behavior involving this domain.

---

## VirusTotal Analysis

No significant detections were observed on VirusTotal at the time of analysis.

This is not unusual because:

* The phishing campaign leveraged trusted cloud infrastructure.
* Recently registered domains often evade reputation-based detections.
* Reputation services frequently lag behind active phishing campaigns.

---

## URL2PNG Analysis

The URL could not be successfully rendered using URL2PNG.

Possible explanations include:

* The hosted object was removed.
* The object was made private.
* The destination changed after campaign deployment.
* The URL relied on client-side redirection.

As a result, the final landing page could not be independently verified using URL2PNG.

---

# Indicators of Compromise (IOCs)

## Domains

```text
sroilknb[.]0il7wqyd[.]com
dfg55fg5dfgfg[.]emprendedesde[.]us[.]com
emprendedesde[.]us[.]com
optimistic-digital[.]xyz
storage[.]googleapis[.]com
```

## Email Addresses

```text
noreply[@]sroilknb[.]0il7wqyd[.]com
```

## IP Addresses

```text
94[.]130[.]230[.]238
185[.]80[.]129[.]75
```

## URLs

```text
hxxps://storage[.]googleapis[.]com/xhr09fe05fe2026/optimisticdigital[.]xyz[.]html

hxxp://optimistic-digital[.]xyz/t/
```

---

# Sources

* Email header analysis
* WHOIS lookup
* VirusTotal
* ANY.RUN sandbox detonation
* URL2PNG

---

# Recommended Actions

1. Block access to:

```text
optimistic-digital[.]xyz
```

2. Add the following domains to email filtering and monitoring controls:

```text
dfg55fg5dfgfg[.]emprendedesde[.]us[.]com

sroilknb[.]0il7wqyd[.]com
```

3. Review historical logs for connections involving:

```text
185[.]80[.]129[.]75

94[.]130[.]230[.]238
```

4. Search for additional emails containing references to:

```text
storage[.]googleapis[.]com/xhr09fe05fe2026/
```

5. Avoid blocking `googleapis[.]com` globally, as it hosts numerous legitimate cloud services and applications.

---

# Conclusion

This phishing campaign utilized Lidl brand impersonation, a recently registered domain, and Google Cloud Storage infrastructure to increase credibility and evade detection. Dynamic analysis confirmed redirect behavior leading to phishing-related infrastructure hosted on `optimistic-digital[.]xyz`.

Based on the collected evidence, this email should be classified as a phishing attempt leveraging trusted cloud infrastructure and prize-themed social engineering techniques.

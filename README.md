# RedNoiseIndex

RedNoiseIndex is a single-page, browser-based planning aid for authorized red-team exercises. It helps security teams discuss how a selected sequence of techniques might appear across endpoint, network, identity, and forensic sensors in a chosen environment—and how a defender might review the resulting telemetry.

It is a planning and discussion tool. It does not execute techniques, scan targets, or make live security checks.

## What it includes

### Environment profile

Configure nine assumptions that affect the estimates:

- EDR platform
- Network monitoring
- Identity monitoring
- Log coverage
- Target host type
- Privilege level
- Time window
- SOC strength
- SOC alert fatigue

Five presets provide starting points: **No EDR (Lab)**, **Corporate Windows**, **MDE + SIEM**, **CrowdStrike Enterprise**, and **Elite MDR**. The profile summary and environment-fit notes help make assumptions visible while building an operation.

### Operation builder and technique catalog

Add ordered phase and technique steps to model an operation. The current catalog contains **46 techniques across eight phases**:

1. Initial Access
2. Recon
3. Credential Access
4. Kerberos Attacks
5. Lateral Movement
6. Defense Evasion
7. C2 & Infrastructure
8. Persistence

Examples include HTML smuggling, host and account discovery, credential-access methods, Kerberoasting, AS-REP Roasting, Golden/Diamond/Silver Tickets, pass-the-ticket, PsExec, WMI, DCOM, WinRM/Evil-WinRM, RDP, PowerShell and sensor-tampering behaviors, command-and-control patterns, scheduled tasks, services, registry run keys, WMI subscriptions, and COM hijacking.

Technique cards can show a description, prerequisites, target types, minimum privilege, MITRE ATT&CK® ID and link, telemetry triggers, illustrative EDR detection likelihood by platform, sensor-dimension estimates, confidence label, and technique-specific validation alternative. The current catalog entries are labeled **Author estimate**. Environment-fit warnings flag modeled privilege or host mismatches.

The operation panel keeps long technique lists in its own scroll area. **Review safer test options** shows scoped, benign validation guidance for selected techniques; it does not automatically replace or modify the selected steps.

### Attacker View

The live analysis area summarizes the selected operation with:

- A five-level signal meter, from **Ghost** to **Screaming**
- Four illustrative sensor dimensions: **Endpoint**, **Network**, **Identity**, and **Forensics**
- An environment-adjusted **OPSEC Debt** estimate from 0 to 100
- Warnings for recognized technique-sequence patterns
- Per-technique breakdowns, triggers, environment fit, and alternatives

The scoring model adjusts estimates to the configured environment. Technical telemetry and SOC response are treated separately: changing SOC coverage, time window, or alert fatigue affects estimated response timing and operational-exposure indicators, not whether a sensor event exists.

### Defender View

The Defender View presents a unified, chronological timeline for the selected operation. It separates illustrative telemetry events from estimated SOC review or response times, and sorts events across the selected techniques. The timeline is context for discussion, not a measured response guarantee.

### Guide and disclaimers

The centered guide dialog contains **Overview**, **How to use**, and **Disclaimer** tabs. It explains the workflow, authorized-use scope, illustrative scoring, environmental limits, local processing, and MITRE attribution. The interface supports keyboard navigation for its tabs and dialog controls.

## How to use it

1. Choose a quick preset or configure the environment settings.
2. Add an operation phase and technique; add more steps to model a sequence.
3. Review the live meter and technique details in **Attacker View**.
4. Switch to **Defender View** to inspect the illustrative timeline and response estimates.
5. Use **Review safer test options** to see benign, scoped validation approaches.

## Run locally or host it

Open `index.html` in a modern browser to run the single-file page locally. The app’s calculations run in the browser and do not require an application backend.

GitHub Pages can publish this as a project site from the repository’s `main` branch and root folder (`/(root)`). GitHub Free includes Pages for public repositories; this setup does not require a paid plan, custom domain, or subscription. A custom domain is optional and may have a separate registrar cost. See [GitHub Pages setup](https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site) and [GitHub’s plan features](https://docs.github.com/en/get-started/learning-about-github/githubs-plans).

GitHub Pages is intended for personal and project showcases, not for running an online business, e-commerce site, or commercial SaaS. See [GitHub Pages terms](https://docs.github.com/en/site-policy/github-terms/github-terms-for-additional-products-and-features).

## Accuracy, safety, and privacy

- Use this planner only for authorized, scoped assessment planning.
- Detection likelihoods, sensor scores, environment factors, sequence correlations, OPSEC Debt, alternatives, privileges, and response timings are author-supplied estimates. They have not been validated against specific product versions, configurations, or production telemetry, and are not guarantees or compliance evidence.
- The page describes techniques but does not run them. Its settings and calculations stay in the browser; the page includes no analytics or data-submission code. External sites open only when a user selects a reference link.
- When hosted, GitHub may process standard request metadata, including visitor IP addresses, for security purposes. See [GitHub Pages privacy information](https://docs.github.com/en/pages/getting-started-with-github-pages/what-is-github-pages#data-collection).
- RedNoiseIndex is independent and is not affiliated with or endorsed by MITRE.

## MITRE ATT&CK® attribution

The catalog uses MITRE ATT&CK® identifiers and mappings. **© 2026 The MITRE Corporation. This work is reproduced and distributed with the permission of The MITRE Corporation.** See the [MITRE ATT&CK Terms of Use](https://attack.mitre.org/resources/terms-of-use/) and [legal and branding guidance](https://attack.mitre.org/resources/legal-and-branding/).

## Suggestions and proposed changes

Suggestions, corrections, feature ideas, and proposed modifications are welcome. After the repository is published, open an Issue with the relevant feature and the change you would like to see, or contact me through [LinkedIn](https://www.linkedin.com/in/sahil-arya-20585b159/). Pull requests with proposed changes are also welcome for review; please do not include confidential client, host, or assessment details.

## Project license

No project license file is currently included. The repository can be public without an open-source license; public visibility lets people view and fork it on GitHub but does not grant general permission to reuse or redistribute the code. The MITRE attribution above applies to the referenced ATT&CK material, not as a license for the RedNoiseIndex project.

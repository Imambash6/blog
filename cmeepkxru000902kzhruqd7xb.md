---
title: "“Who has root access in your org?”"
seoTitle: "Who Has Root Access in Your Org? Why Cloud-Native PAM Beats Static Key"
seoDescription: "“Traditional security fails in cloud-native. At CNCF Abuja, I demoed how PAM evolved from static keys to identity-first access.”"
datePublished: Sat Aug 16 2025 20:27:36 GMT+0000 (Coordinated Universal Time)
cuid: cmeepkxru000902kzhruqd7xb
slug: who-has-root-access-in-your-org
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/nyLV3a2zYRI/upload/d11fe2a09e50f19932ca1678d5c92e26.jpeg
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1755375913119/c36e9835-e5af-4995-95fa-ce3016511796.png
tags: aws, opensource, security, pam, teleport

---

I walked through this in [my demo](https://www.linkedin.com/posts/imambashir_devops-cloud-aws-activity-7354534863191916545-Limt?utm_source=share&utm_medium=member_desktop&rcm=ACoAAB95ouEBz9JzCbQfqRpeJvtIKRkUeG36Dhk) at CNCF Abuja last month, showing how modern, identity-first access makes that question easy to answer.

Now be honest, are you still babysitting SSH keys, bouncing through hosts, and praying your audit logs tell the full story? Yeah… been there. That’s why I wanted to show you something different: **Teleport**.

### So, what’s Teleport?

Think of it as an *identity-native access superpower* that makes your DevOps life a little less chaotic:

* SSH servers ✅
    
* Kubernetes clusters ✅
    
* Databases ✅
    
* Internal apps ✅
    
* Even Windows desktops lol (because yes, those still exist) ✅
    

One way in. One audit trail. Nothing left sitting around on disk for bad actors to scoop up.

### Why you (and your team) might actually love this:

* No more passing around shared keys like it’s 09’s
    
* Access expires by default (because eternal credentials are a horror story)
    
* Full session recording + audit logs for the “what just happened” moments
    
* Plug into GitHub, Okta, Google, whatever you already use for login
    
* Bye-bye VPNs and sketchy tunnels
    

### Security, but with common sense

Teleport doesn’t wrap your infra in duct tape. It enforces *identity-based, short-lived certs*. No passwords, no long-lived keys, no “oops I left that open.”

* Everything logs.
    
* Everything has a policy.
    
* Everything expires. (…kind of like milk, but way more useful).
    

### Wanna try it out right now?

*Here’s the fun part:*

![This is Teleport on my EC2 Instance for Demo](https://cdn.hashnode.com/res/hashnode/image/upload/v1755374536221/7aa6877b-4858-4a90-b65c-0fab2d8333b6.png align="center")

1. Launch the open-source version with Docker or host cloud-based on your server.
    
2. Wire up a test cluster and local SSH.
    
3. Hook in GitHub or OIDC SSO.
    
4. Write some RBAC rules in YAML (don’t panic, it’s actually neat).
    
5. Watch your own session recordings in the web UI, creepy but powerful.
    

Pick your flavor from *what’s available!*

| ***Tier*** | ***Best for*** | ***Includes*** |
| --- | --- | --- |
| *Teleport Community (OSS)* | Indie DevOps, startups or side projects | Basic access for SSH, K8s, DBs |
| *Teleport Enterprise* | Regulated orgs, large teams | SSO, session replay, RBAC, audit |
| *Teleport Cloud* | Teams that want SaaS setup *(I don’t want to host it, just make it work)* | No self-hosting, auto-upgrades |
| *Teleport Team* | Mid-size orgs *(like SaaS but want control)* | Cloud-hosted with most features |

### If you’re still unsure where to start? Use this cases to steal:

![An onboarded Amazon server onboarded as a resource on teleport](https://cdn.hashnode.com/res/hashnode/image/upload/v1755374657411/9023578d-1fcf-404a-8872-f8aafa43670a.png align="center")

* Secure SSH across multi-cloud setups
    
* Jump into K8s clusters without juggling kubeconfigs
    
* Lock down your DBs (Postgres, MongoDB, MySQL)
    
* Retire that poor bastion host that’s been clinging to life
    
* Impress compliance folks (SOC2, PCI-DSS, FedRAMP)
    

👉 [teleport.dev/pricing](https://teleport.dev/pricing)

💡 *Pro tip:* Engineers can request *just-in-time access* and managers approve right inside Slack, PagerDuty, or even CLI. No tickets, no back-and-forth emails, just “yes” or “no” in real-time.

### Bonus: Plays nice with others

Already using GitHub Actions, Vault, Terraform, AWS/GCP? Teleport slots right in without making you rethink your stack.

> 🎤 **My takeaway from demoing this at** [**<mark>CNCF</mark>**](https://www.linkedin.com/posts/imambashir_devops-cloud-aws-activity-7354534863191916545-Limt?utm_source=share&utm_medium=member_desktop&rcm=ACoAAB95ouEBz9JzCbQfqRpeJvtIKRkUeG36Dhk) **last month?**  
> If your infra is scaling but your access model still looks like “static IAM roles + ancient SSH keys,” Teleport is the glow-up you didn’t know you needed.
# Agile Testing Principles

## General 

### Quality is everyone's responsibility
Quality in testing is a shared responsibility across the entire team.
We must move away from labeling work as “Dev Complete” or “Test Complete” — there is only one team, collectively accountable for delivering a high-quality product.

Quality should be built in, not inspected later. It starts from requirement discussions and continues through development, testing, and production.
Break down silos, promote open communication, and build trust across roles — Developers, QA, Product, and DevOps — all contribute to the same goal: a reliable, secure, and valuable product for users.

Adopt an agile, continuous quality mindset: prevent issues early, automate smartly, and ensure every release increases confidence and user trust.
Quality isn’t a phase — it’s how we work, care, and deliver together.

| ✅ **Good Things (Shared Quality Mindset)** | ❌ **Bad Things (Role-Based Thinking)** |
|---------------------------------------------|----------------------------------------|
| We build quality together — one team, one goal. | “Dev Complete” / “Test Complete” divides us and slows progress. |
| Everyone cares — Dev, QA, PO, PM all protect user trust. | “That’s not my job” leads to blame, confusion, and waste. |
| Faster, smoother releases — fewer bugs, more confidence. | Late testing causes chaos, stress, and rework. |
| Open communication — problems solved before they grow. | Silence between roles means surprises at the end. |
| Shared success — we celebrate quality as a team win. | Finger-pointing kills motivation and trust. |


### Zero known bugs approach
A Zero Known Bug Policy is simple concept. All bugs take priority over all new feature development or improvements. That’s it. There is nothing more.
An important corollary of this approach is that there is no such thing as bug priority, critical bugs, or minor bugs. An issue is either a bug or it isn’t. And if it is a bug, you need to fix it before doing other work.

Zero Known Bug does not mean bug-free code production; it means striving to eradicate all known bugs. <br/>

It is impossible for people to continuously produce bug-free, production ready code. Bugs will always
exist. The issue should be known and	by labels like:

  Critical Issues : fix immediately <br/>
  Bugs : finish current work and fix bugs <br/>
  Features : work in backlog priority order <br/>
  Improvements : work in backlog priority order <br/>
  
<img width="369" alt="image" src="https://github.com/user-attachments/assets/8b574c8f-322e-4280-9b76-15a10365fae2">

### Shifting Left, Shifting Right
The idea of this is: if an issue is discovered on production after you go live it is a very expensive problem. If an issue is found before deploying on production, it can take a lot of effort to reproduce, fix but it’s still a expensive. If an issue is known before merging code (review stage), it is cheaper but it still required a bit of effort to work. If problem can be detected on local, discussion, or cross-test that is always cheapest than other. <br/>
<img width="368" alt="image" src="https://github.com/user-attachments/assets/a6e4d54f-ddff-4aee-9a2c-875cfd8dbde4">






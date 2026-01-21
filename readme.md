# DailyEdge Rendering Strategy  
**Case Study: “The News Portal That Felt Outdated”**

This project explores how to balance **speed, freshness, and scalability** using different rendering strategies in Next.js App Router.

You can’t maximize all three at once — every rendering mode gives you two easily and sacrifices one.

---

## The Triangle of Trade-offs

- ⚡ Speed – How fast the page loads  
- 🧠 Freshness – How up-to-date the content is  
- 💸 Scalability – How well the system handles traffic without huge cost  

| Mode     | Speed | Freshness | Scalability |
|----------|-------|-----------|-------------|
| Static   | ✅    | ❌        | ✅          |
| Dynamic  | ❌    | ✅        | ❌          |
| Hybrid   | ✅    | ✅        | ⚠️         |

---

## Rendering Modes

### 1. Static Rendering (SSG)

- Page is built once and served from CDN.
- Extremely fast and cheap.
- But content becomes outdated.

Example:
``ts
export const revalidate = false;

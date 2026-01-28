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







#2

## Environment Configuration & Secrets Management

This project uses strict environment isolation to prevent
cross-environment data corruption.

### Environments
- Development
- Staging
- Production

Each environment has:
- Separate configuration
- Separate secrets
- Separate databases

### Secrets Handling
- No secrets are committed to Git
- Secrets are injected via CI/CD
- Environment variables are validated at startup

### Safety Checks
- Production builds refuse non-production credentials
- Database access is restricted per environment






#3


## Deployment Architecture Overview

This project uses containerized, versioned deployments
with strict environment variable management to ensure
consistent production behavior.

### Containerization Principles
- One service = one container
- Immutable images (no SSH into prod)
- Versioned Docker images (not `latest`)

### Environment Variables
- No `.env` files in production
- All variables injected via CI/CD or cloud secrets
- Containers fail fast if required variables are missing

### Deployment Strategy
- Old containers are stopped before new ones start
- Health checks determine traffic readiness
- Only one active version serves production traffic

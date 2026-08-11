# Turborepo monorepo with Next.js Landing app

DTM ONES is a multi-app product; we structure the repo as a **Turborepo** monorepo and implement the public marketing site as **`apps/landing`** on **Next.js**. That keeps the Landing context isolated for a UI-first build while leaving room for a second app later, without splitting repos. Alternatives considered: a single Next.js repo (rejects early multi-app shape) or a non-Next marketing stack (worse fit for the full Player UI and shared JS tooling).

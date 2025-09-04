# Geojit Diwali Muhurat Trading – Hyper‑Personalised MVP (Standalone)

This bundle contains **A/B/C**:
- **A. Backend schema + sample data + API stubs + LLM prompt templates**
- **B. Minimal Next.js UI scaffold (chat + portfolio) with mock API that runs without external keys**
- **C. Persona fixtures + demo portfolios**

## Quick Start (Mock Mode — no keys needed)
1. Install Node 18+ and pnpm or npm.
2. `cd frontend/nextjs`
3. `cp .env.example .env.local`  (MOCK_MODE=true by default)
4. `pnpm install` (or `npm install`)
5. `pnpm dev` (or `npm run dev`)
6. Open http://localhost:3000 and walk through OTP → quiz → amount → portfolio → queue.
   - API routes use data from `fixtures/` to simulate results.

## Switching to Real Backend (Supabase + LLM)
1. Create a Supabase project. Run SQL in `backend/schema.sql`.
2. Import `backend/sample_research_ideas.csv` to `research_ideas` table.
3. Add your env vars in `frontend/nextjs/.env.local` (see file for keys).
4. Flip `MOCK_MODE=false` and implement DB access in `/app/api/*/route.ts` stubs (marked TODO).
5. Connect your LLM provider; use prompt templates in `backend/prompt_templates/*` for rationale generation.
6. (Optional) Wire MoEngage & Sentry (placeholders included).

## Structure
- `backend/` – SQL schema, CSV sample, TS stubs for ideas engine.
- `frontend/nextjs/` – Next.js App Router UI + API routes.
- `fixtures/` – Personas and demo portfolios (used in mock mode).

## Notes
- Language kept as **"investment ideas"**. Disclaimers added.
- All numbers in portfolios are for demo only.
- This is an MVP for internal demonstration; harden security/compliance before production.

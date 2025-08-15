# Your ChatGPT on Vercel

A minimal Next.js app that streams responses from OpenAI’s **Responses API**. Use your own API key either via server env (`OPENAI_API_KEY`) or paste per-session in the UI.

## Local dev

1. `pnpm i` or `npm i` or `yarn`
2. Create `.env.local` and set:
   OPENAI_API_KEY=sk-...
3. `npm run dev`

## Deploy on Vercel

1. Push to GitHub.
2. Import the repo at https://vercel.com/import
3. In **Vercel → Project → Settings → Environment Variables** add:
   - `OPENAI_API_KEY` = your key (Production + Preview + Development)
4. Deploy.

## Notes

- We stream via Next.js Route Handler on the Edge runtime for low-latency streaming on Vercel.
- If you paste an API key in the UI, it is stored only in your browser (optional checkbox). For maximum safety, prefer the server env variable.
- Default model: `gpt-4o`. Switch to `gpt-4o-mini` to reduce cost. 

# project-college-ai-interview-app-2210990037
# AI Interview Preparation App — Backend (SQL + Prisma)

A runnable Node.js + Express + PostgreSQL (via Prisma) backend for the AI-powered interview practice app.

## Quick Start

1. **Install PostgreSQL** and create a database:
   ```bash
   createdb ai_interview
   ```

2. **Clone / extract this folder**, then install dependencies:
   ```bash
   npm install
   ```

3. **Create `.env`** from `.env.example` and update values:
   - `DATABASE_URL` for your Postgres
   - `OPENAI_API_KEY` for question generation and grading

4. **Prisma setup & DB migration:**
   ```bash
   npx prisma generate
   npm run prisma:migrate
   ```

5. **(Optional) Seed sample data:**
   ```bash
   npm run seed
   ```

6. **Run the server:**
   ```bash
   npm run dev
   ```

   API base: `http://localhost:5001/api`

## Auth
- JWT in HTTP-only cookie (`token`)
- Register: `POST /api/auth/signup`
- Login: `POST /api/auth/login`
- Me: `GET /api/auth/me`

## Interview Flow
1. Create interview: `POST /api/interviews` with `{ topic, difficulty }`
2. Generate a question: `POST /api/questions/generate` with `{ interviewId }`
3. Submit an answer: `POST /api/answers` with `{ questionId, userResponse }`
4. Fetch analytics: `GET /api/analytics`

## Notes
- Analytics are computed on-the-fly from answers.
- Swap models by editing `OPENAI_MODEL` in `.env`.


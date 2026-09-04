# WinkPass — Vercel Ready

WinkPass is a browser-based ocular gesture password demo using MediaPipe Face Mesh and a Flask API.

## Run locally

### Option 1 — Vercel-style full stack

```powershell
npm install -g vercel
vercel dev
```

Open `http://localhost:3000` and allow camera access.

### Option 2 — Flask backend

```powershell
python -m venv .venv
.\.venv\Scripts\Activate.ps1
pip install -r requirements.txt
python server.py
```

The Flask server runs at `http://127.0.0.1:5000`.

## Deploy to Vercel

1. Push this folder to GitHub.
2. Import the repository into Vercel.
3. Keep the project root as the repository root.
4. Deploy.
5. Open the generated HTTPS URL and allow webcam access.

The browser performs MediaPipe processing locally; only the detected gesture sequence is sent to `/api/verify` or `/api/enroll`.

## Default demo password

LEFT → RIGHT → LEFT → BOTH

## Important demo limitation

The Flask backend currently stores the master hash and audit logs in memory. Serverless instances are not a durable database, so this is suitable for a makeathon/demo rather than production authentication.

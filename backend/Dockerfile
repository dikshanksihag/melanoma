# ============================================================
# Backend Dockerfile
# Phase 4 | FastAPI melanoma inference server
# ============================================================

FROM python:3.10-slim

# ── System dependencies ───────────────────────────────────────────────────────
RUN apt-get update && apt-get install -y \
    gcc \
    git \
    && rm -rf /var/lib/apt/lists/*

# ── Working directory ─────────────────────────────────────────────────────────
WORKDIR /app

# ── Install Python dependencies ───────────────────────────────────────────────
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

# ── Copy backend source ───────────────────────────────────────────────────────
COPY . .

# ── Create logs directory ─────────────────────────────────────────────────────
RUN mkdir -p logs

# ── Expose port ───────────────────────────────────────────────────────────────
EXPOSE 8000

# ── Start FastAPI with uvicorn ────────────────────────────────────────────────
CMD ["uvicorn", "main:app", "--host", "0.0.0.0", "--port", "8000", "--reload"]
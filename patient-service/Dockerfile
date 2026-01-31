# ---------- Stage 1: Build ----------
FROM node:18-alpine AS builder

WORKDIR /app

COPY package*.json ./

# install deps (no lock file → use install)
RUN npm install --omit=dev

COPY src ./src


# ---------- Stage 2: Runtime ----------
FROM node:18-alpine

WORKDIR /app

COPY --from=builder /app/node_modules ./node_modules
COPY --from=builder /app/src ./src

ENV NODE_ENV=production
ENV PORT=3000

EXPOSE 3000

CMD ["node", "src/index.js"]

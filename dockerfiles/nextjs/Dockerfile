FROM refinedev/node:1.0.0 AS base

FROM base AS deps

RUN apk add --no-cache libc6-compat

COPY package.json yarn.lock* package-lock.json* pnpm-lock.yaml* .npmrc* ./

RUN \
    if [ -f yarn.lock ]; then yarn --frozen-lockfile; \
    elif [ -f package-lock.json ]; then npm ci; \
    elif [ -f pnpm-lock.yaml ]; then yarn global add pnpm && pnpm i --frozen-lockfile; \
    else echo "Lockfile not found." && exit 1; \
    fi

FROM base AS builder

COPY --from=deps /app/refine/node_modules ./node_modules

COPY . .

ENV NEXT_TELEMETRY_DISABLED 1

RUN npm run build

FROM base as production-deps

COPY --from=deps /app/refine/node_modules ./node_modules

COPY package.json yarn.lock* package-lock.json* pnpm-lock.yaml* .npmrc* ./

ENV NODE_ENV production

RUN npm prune

FROM base AS runner

ENV NODE_ENV production
ENV NEXT_TELEMETRY_DISABLED 1

COPY --from=builder /app/refine/public ./public

RUN mkdir .next
RUN chown refine:nodejs .next

COPY --from=production-deps --chown=refine:nodejs /app/refine/node_modules ./node_modules
COPY --from=builder --chown=refine:nodejs /app/refine/.next/standalone ./
COPY --from=builder --chown=refine:nodejs /app/refine/.next/static ./.next/static
COPY --from=builder --chown=refine:nodejs /app/refine/package.json ./package.json

USER refine

EXPOSE 3000

ENV PORT 3000
ENV HOSTNAME "0.0.0.0"

CMD ["node", "server.js"]
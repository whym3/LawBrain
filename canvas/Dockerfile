# Build stage
FROM node:20-alpine AS builder
WORKDIR /app

# Copy package files
COPY package.json yarn.lock ./
COPY apps/web/package.json apps/web/
COPY apps/agents/package.json apps/agents/
COPY packages/shared/package.json packages/shared/

# Install root dependencies with forced resolutions
RUN yarn install --ignore-scripts --check-files

# Copy all files including .env
COPY . .
COPY .env.example .env
COPY apps/web/.env.example apps/web/.env

# Web service image
FROM node:20-alpine AS web
WORKDIR /app

# Copy built artifacts
COPY --from=builder /app/node_modules ./node_modules
COPY --from=builder /app/apps/web ./apps/web
COPY --from=builder /app/packages ./packages

WORKDIR /app/apps/web
EXPOSE 3000
CMD ["yarn", "dev"]

# Agents service image
FROM node:20-alpine AS agents
WORKDIR /app

# Copy built artifacts
COPY --from=builder /app/node_modules ./node_modules
COPY --from=builder /app/apps/agents ./apps/agents
COPY --from=builder /app/packages ./packages
COPY --from=builder /app/langgraph.json ./

WORKDIR /app/apps/agents
EXPOSE 54367
CMD ["yarn", "dev"]

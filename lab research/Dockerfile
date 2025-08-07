FROM node:24-slim

USER root

RUN apt-get update && apt-get install -y --no-install-recommends \
    curl \
    nmap \
    netcat-openbsd \
    iputils-ping \
    stress \
 && rm -rf /var/lib/apt/lists/*

WORKDIR /app
COPY . .
RUN npm install express@4.21.2

RUN useradd -m appuser && chown -R appuser /app
USER appuser

# ❌ Expose unnecessary ports
EXPOSE 22
EXPOSE 3000

CMD ["node", "server.js"]


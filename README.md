# ReadMe – Infraestructura

## Configuración

```bash
cp .env.example .env
```

Editar `.env`:
- Reemplazar `<ip-vm-bds>` con la IP privada de la VM de BDs en `DB_HOST` y `MONGO_URL`
- Rellenar el resto de variables vacías

## Levantar

```bash
# BDs (ejecutar en VM de BDs)
docker compose -f docker-compose.dbs.yml up -d

# Microservicios (ejecutar en VM de servicios)
docker compose up -d

# Seeder — solo una vez, después de levantar BDs y MS
docker compose -f docker-compose.seed.yml run --rm seeder
```

## Bajar

```bash
# Microservicios
docker compose down

# BDs
docker compose -f docker-compose.dbs.yml down
```

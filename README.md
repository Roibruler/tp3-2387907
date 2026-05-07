# TP3 - Déploiement multi-service sur AWS

## Services déployés

- **Traefik** - Reverse proxy avec HTTPS automatique (Let's Encrypt)
- **Portainer** - Interface de gestion Docker (`portainer.tp3-2387907.duckdns.org`)
- **Jellyfin** - Serveur multimédia (`jellyfin.tp3-2387907.duckdns.org`)
- **BlogVerse** - Application de blog full-stack (`blogverse.tp3-2387907.duckdns.org`)

## Déploiement

```bash
git clone --recurse-submodules https://github.com/Roibruler/tp3-2387907.git
cd tp3-2387907
cp .env.example .env
# Remplir les valeurs dans .env
mkdir -p ../data/traefik/letsencrypt
sudo docker compose up -d
```

## Variables d'environnement

Voir `.env.example` pour la liste complète.

| Variable | Description |
|---|---|
| `MY_EMAIL` | Email pour Let's Encrypt |
| `MY_DOMAIN` | Domaine DuckDNS |
| `DUCKDNS_TOKEN` | Token DuckDNS pour le certificat SSL |
| `MYSQL_*` | Identifiants base de données BlogVerse |
| `JWT_SECRET` | Clé secrète pour l'authentification |

# Proxy Nginx pour VPS (159.89.80.171)

Proxy Nginx déployé sur Google Cloud Run pour rediriger le trafic TCP vers le VPS principal.

## Configuration
| Élément | Valeur |
|---------|--------|
| **VPS cible** | `159.89.80.171:443` |
| **Port d'écoute proxy** | `8080` |
| **Région VPS** | `us-east4` (New York / Virginie du Nord, USA) |
| **Région Cloud Run** | `africa-south1` (Johannesburg, Afrique du Sud) |
| **Type de proxy** | TCP Stream (Layer 4) |

## Déploiement
```bash
gcloud run deploy ultra-speed-proxy \
  --source . \
  --platform managed \
  --region africa-south1 \
  --allow-unauthenticated \
  --port 8080 \
  --memory 512Mi \
  --cpu 1 \
  --timeout 3600

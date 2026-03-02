# reto-tecnico-devsu
Reto Técnico Ingeniero Cloud

# Arquitectura Cloud – SPA Angular + API ASP.NET Core en AWS

Este repositorio documenta la arquitectura cloud de una aplicación web moderna compuesta por:

- Frontend SPA (Angular / React)
- Backend API (ASP.NET Core 10)
- Reverse Proxy (Nginx)
- Infraestructura en AWS con enfoque en seguridad, escalabilidad y buenas prácticas enterprise

---

## 🏗️ Arquitectura General

La solución implementa un patrón de **single entry point** con CDN y reverse proxy, donde:

- El frontend se distribuye desde :contentReference[oaicite:0]{index=0} con origen en :contentReference[oaicite:1]{index=1}  
- Las llamadas a `/api` son enroutadas hacia un :contentReference[oaicite:2]{index=2}  
- El ALB redirige el tráfico al reverse proxy Nginx desplegado en :contentReference[oaicite:3]{index=3}  
- Nginx reenvía las peticiones al backend ASP.NET Core, también en ECS  
- El backend accede a la base de datos en :contentReference[oaicite:4]{index=4} (SQL Server Standard)  
- Backend y base de datos se encuentran en subred privada y no están expuestos a internet

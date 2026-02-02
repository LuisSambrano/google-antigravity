---
description: Aplica los estándares globales de Antigravity (Vibecode Pro Max + Next.js Strict) a un proyecto existente.
---

# Workflow: Standardize Project

Este flujo audita y refactoriza un proyecto para cumplir con los estándares globales definidos en `../rules/`.

## Proceso de Ejecución (Agente)

1.  **Auditoría**:
    - Revisar `package.json`: ¿Tiene `framer-motion`, `lucide-react`, `tailwind-merge`?
    - Revisar `app/layout.tsx`: ¿Están configuradas las fuentes (Inter/Outfit)?
    - Revisar `tailwind.config.ts`: ¿Contiene los colores "Luxury"?

2.  **Inyección de Reglas (Frontend)**:
    - Lee `../rules/frontend/nextjs-strict.md`.
    - Lee `../rules/frontend/ui-ux-luxury.md`.
    - Aplica Glassmorphism a los componentes principales.

3.  **Inyección de Reglas (Backend)**:
    - Lee `../rules/backend/supabase-security.md`.
    - Verifica que los clientes de Supabase usen el patrón Singleton.

## Instrucciones para el Operador

Para ejecutar este workflow en un repo (ej: `Puente`):

1.  Abre el directorio del proyecto.
2.  Invoca al agente: _"Ejecuta el workflow de estandarización global"_.
3.  El agente leerá este archivo y procederá paso a paso.

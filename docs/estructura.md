# Estructura del Proyecto

Este proyecto combina Next.js (App Router) con Payload CMS.

| Carpeta        | Descripción                                     |
|----------------|-------------------------------------------------|
| `/app`         | Rutas del frontend con Next.js                  |
| `/payload`     | Backend headless CMS (colecciones, hooks, etc.)|
| `/actions`     | Server Actions para comunicación directa        |

## Código de ejemplo

=== "Next.js App"

    ```tsx
    export default function Page() {
      return <h1>Foros</h1>;
    }
    ```
=== "Payload CMS Collection"

    ```ts
    import { CollectionConfig } from 'payload/types';

    export const Forums: CollectionConfig = {
        slug: 'forums',
        fields: [{ name: 'title', type: 'text' }],
    };

    ```
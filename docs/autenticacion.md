!!! tip 
Organiza tus carpetas de forma coherente para facilitar la escalabilidad del proyecto.
---

# Autenticación

El sistema de autenticación usa `next-auth` con Payload CMS como proveedor personalizado.

!!! warning
No uses localStorage para guardar JWT. Siempre usa cookies seguras con `HttpOnly`.

## Flujo

1. El frontend envía el correo y contraseña a un endpoint.
2. El backend responde con un JWT si es válido.
3. El JWT se guarda como cookie en el navegador.

## Código de ejemplo

=== "API Login en Next.js"

    ```ts
    import { NextResponse } from 'next/server';
    import payload from 'payload';

    export async function POST(req: Request) {
        const { email, password } = await req.json();
        const user = await payload.login({ email, password });
        return NextResponse.json(user);
    }
    ```

=== "Formulario de inicio de sesión"

    ```tsx
    <form action="/api/login" method="POST">
      <input type="email" name="email" required />
      <input type="password" name="password" required />
      <button>Entrar</button>
    </form>

    ```
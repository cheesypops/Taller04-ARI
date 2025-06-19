
---

# Publicación de Contenido

Con Payload CMS puedes crear colecciones como foros, temas y comentarios, y gestionarlos desde el frontend.

!!! note
Puedes usar `useForm` o `server actions` para manejar la creación de contenido.

## Crear un tema desde el frontend

=== "Server Action"

    ```ts
    'use server';

    export async function addTheme(data) {
        const res = await fetch('http://localhost:3000/api/themes', {
            method: 'POST',
            body: JSON.stringify(data),
        });
        return res.json();
    }
    ```
=== "Formulario en React"

    ```tsx
    <form action={addTheme}>
        <input name="title" required />
        <button type="submit">Crear</button>
    </form>

    ```

| Rol    | Permisos                     |
|--------|------------------------------|
| Admin  | Todo (crear, editar, borrar) |
| Editor | Crear y editar               |
| Viewer | Solo lectura                 |

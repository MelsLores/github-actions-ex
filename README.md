# Spring Boot + Vercel

Proyecto base de Spring Boot listo para ejecutar localmente y preparar despliegue con Vercel.

## Stack

- Java 21
- Spring Boot
- Maven Wrapper (`./mvnw`)

## Endpoint de prueba

- `GET /api/hello`
- Respuesta esperada:

```json
{
	"message": "Spring Boot en Vercel listo"
}
```

## Ejecutar local

```bash
./mvnw spring-boot:run
```

Luego prueba:

```bash
curl http://localhost:8080/api/hello
```

## Tests

```bash
./mvnw test
```

## Despliegue en Vercel

### 1) Conectar el repo en Vercel

- Importa este repositorio desde el dashboard de Vercel.

### 2) Variables/secretos necesarios en GitHub

En tu repositorio de GitHub, configura estos secretos:

- `VERCEL_TOKEN`
- `VERCEL_ORG_ID`
- `VERCEL_PROJECT_ID`

### 3) Flujo automático

El workflow `.github/workflows/vercel-deploy.yml`:

- ejecuta tests en `pull_request` y `push`
- despliega a producción en `push` a `main`

## Nota sobre GitHub Pages

GitHub Pages solo publica contenido estático y no ejecuta backend Java/Spring Boot. Para apps Spring Boot, usa una plataforma de runtime backend como Vercel, Render, Railway o similares.
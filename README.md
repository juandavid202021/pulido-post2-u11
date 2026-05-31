# Catálogo de Productos — Post-Contenido 2, Unidad 11

Integración de **SLF4J/Logback** para logging con niveles apropiados y rotación de archivos, y documentación de la API REST con **Swagger/OpenAPI** mediante springdoc-openapi.

---

## Prerrequisitos

- Java 17 o superior
- Maven 3.9.x
- Proyecto del Post-Contenido 1 como base

---

## Clonar el repositorio

```bash
git clone https://github.com/juandavid202021/pulido-post2-u11.git
cd pulido-post2-u11/catalogo
```

---

## Instrucciones de ejecución

### Compilar

```bash
mvn compile
```

### Iniciar la aplicación

```bash
mvn spring-boot:run
```

La aplicación arranca en `http://localhost:8080`.

---

## Acceso a Swagger UI

Con la aplicación corriendo, abre en el navegador:
http://localhost:8080/swagger-ui.html

También puedes ver el JSON de la especificación OpenAPI en:
http://localhost:8080/api-docs

---

## Archivos de Log

Los logs se generan automáticamente en la carpeta `logs/` en la raíz del proyecto:
pulido-post2-u11/
└── catalogo/
└── logs/
└── catalogo.log
└── catalogo.2026-05-31.log

Para ver el contenido del log desde la terminal:

```bash
# Windows PowerShell
cat logs/catalogo.log

# Windows CMD
type logs\catalogo.log
```

Los logs se rotan diariamente y se conservan hasta **30 días** de historial.

---

## Niveles de Log configurados

| Nivel | Cuándo se usa |
|-------|--------------|
| INFO | Operaciones exitosas (crear, eliminar producto) |
| DEBUG | Consultas y búsquedas |
| WARN | Recurso no encontrado |
| ERROR | Excepciones inesperadas |

---

## Endpoints documentados

| Método | URL | Descripción | Status |
|--------|-----|-------------|--------|
| GET | /api/productos | Lista todos los activos | 200 |
| GET | /api/productos/{id} | Busca por ID | 200 / 404 |
| POST | /api/productos | Crea nuevo producto | 201 / 400 |
| DELETE | /api/productos/{id} | Elimina por ID | 204 / 404 |

---

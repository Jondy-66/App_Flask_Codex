Análisis de la Seguridad de Código Fuente Desarrollado con Asistencia GenAI

![Python](https://img.shields.io/badge/Python-3.10%2B-blue?style=flat&logo=python&logoColor=white)
![Flask](https://img.shields.io/badge/Flask-3.0%2B-green?style=flat&logo=flask&logoColor=white)
![OWASP](https://img.shields.io/badge/OWASP-Top%2010%3A%202025-red?style=flat&logo=owasp&logoColor=white)
![CVSS](https://img.shields.io/badge/CVSS-v4.0-purple?style=flat)

Este repositorio contiene los artefactos de software generados y auditados como parte del Trabajo de Fin de Máster (TFM) del Máster Universitario en Ciberseguridad de la Universidad Internacional de La Rioja (UNIR). El proyecto evalúa empíricamente la seguridad por defecto del código generado por tres de los Modelos de Lenguaje Grande (LLMs) más extendidos de la industria bajo condiciones zero-shot.

# Aplicacion Flask: autenticacion, empleados y subida de archivos

Proyecto listo para ejecutar con Flask, SQLite y Bootstrap por CDN.

## Funcionalidades

- Registro, login, logout y sesiones de usuario.
- Recuperacion de contrasena con token temporal y envio simulado en consola/interfaz.
- CRUD web de empleados: crear, listar, buscar por ID, ver, editar y eliminar.
- API REST de empleados:
  - `GET /api/employees`
  - `POST /api/employees`
  - `GET /api/employees/<id>`
  - `PUT /api/employees/<id>`
  - `DELETE /api/employees/<id>`
- Alias compatibles:
  - `GET /employees/api`
  - `POST /employees/api`
  - `GET /employees/api/<id>`
  - `PUT /employees/api/<id>`
  - `DELETE /employees/api/<id>`
- Carga de archivos protegida por sesion en `/uploads`.
- SQLite con tablas relacionales e integridad referencial.

## Instalacion local

```bash
python -m venv .venv
.venv\Scripts\activate
pip install -r requirements.txt
python run.py
```

Luego abre `http://127.0.0.1:5000`.

## Configuracion para produccion

Crea variables de entorno seguras:

```bash
SECRET_KEY=una-clave-larga-y-aleatoria
DATABASE_URL=C:\ruta\segura\app.sqlite3
UPLOAD_FOLDER=C:\ruta\segura\uploads
MAX_CONTENT_LENGTH=5242880
```

Ejemplo con Gunicorn en Linux:

```bash
gunicorn "wsgi:app"
```

Para produccion real, usa HTTPS, una `SECRET_KEY` fuerte, backups de base de datos, almacenamiento persistente para `uploads` y un servidor WSGI administrado por systemd, Docker o la plataforma cloud elegida.

👥 Autores y Equipo de Investigación

Trabajo de investigación empírica desarrollado por:

César Augusto Salazar Valdez — Auditoría y análisis de Gemini

Jonathan Gonzalo Diaz Angulo — Auditoría y análisis de ChatGPT

Oscar Dario Lopez Jimenez — Auditoría y análisis de Claude

Universidad Internacional de La Rioja (UNIR) — 2026.

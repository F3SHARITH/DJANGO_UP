# Gestión Académica · API

Servicio para administrar la información de una **institución educativa**: estudiantes, docentes, cursos, matrículas, notas, horarios, pagos y más.

## ¿Qué incluye?

El servicio ofrece 30 recursos, agrupados así:

| Área | Recursos |
|---|---|
| **Institución** | Periodos académicos, departamentos, edificios, aulas y calendario de eventos |
| **Personas** | Personas, estudiantes, docentes y usuarios |
| **Oferta académica** | Programas, cursos, prerrequisitos, grupos, syllabus y sus unidades, material de curso |
| **Vida académica** | Matrículas y su historial, horarios, asistencia, evaluaciones, notas, calificaciones finales y tutorías |
| **Trámites** | Becas, pagos, homologaciones, solicitudes académicas y sanciones |
| **Control** | Auditoría |

Todos los recursos están disponibles bajo la dirección `/api/v1/`.

## Herramientas

| Herramienta | Para qué se usa |
|---|---|
| [Python](https://www.python.org/) | Lenguaje del proyecto |
| [Django](https://www.djangoproject.com/) | Framework principal y panel de administración |
| [Django REST Framework](https://www.django-rest-framework.org/) | Crear las direcciones por las que otras aplicaciones consultan y envían datos |
| [PostgreSQL](https://www.postgresql.org/) | Base de datos |
| [python-decouple](https://github.com/HBNetwork/python-decouple) | Leer la configuración privada desde un archivo `.env` |

## Cómo está organizado

```text
api/
├── models.py       → Tablas de la base de datos
├── serializers.py  → Conversión de los datos a formato JSON
├── views.py        → Lógica de cada recurso
└── urls.py         → Direcciones disponibles
backent/            → Configuración general del proyecto
run.py              → Inicia el servidor en el puerto configurado
```

## Cómo ejecutarlo

Necesitas tener instalados [Python](https://www.python.org/downloads/) y [PostgreSQL](https://www.postgresql.org/download/).

1. Instala las dependencias:

```bash
pip install django djangorestframework psycopg2-binary python-decouple
```

2. Crea un archivo `.env` en la raíz del proyecto:

```env
SECRET_KEY=escribe-una-clave-larga
DEBUG=True
ALLOWED_HOSTS=127.0.0.1,localhost
API_PORT=8000
DB_NAME=gestion_academica
DB_USER=tu_usuario
DB_PASSWORD=tu_contraseña
DB_HOST=localhost
DB_PORT=5432
DB_SCHEMA=public
```

3. Crea las tablas e inicia el servidor:

```bash
python manage.py migrate
python run.py
```

4. Abre <http://localhost:8000/api/v1/> en el navegador.

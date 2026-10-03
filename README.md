# 💳 TaskBoard — Semana 9 (Formularios)

> Proyecto integrador de **Integración de Sistemas (CE-ISC019)** — se construye el formulario para registrar transacciones reales.

![Laravel](https://img.shields.io/badge/Laravel-11.x-FF2D20?style=for-the-badge&logo=laravel&logoColor=white)
![Blade](https://img.shields.io/badge/Blade-Formularios-F7523F?style=for-the-badge&logo=laravel&logoColor=white)
![PHP](https://img.shields.io/badge/PHP-8.2+-777BB4?style=for-the-badge&logo=php&logoColor=white)
![License](https://img.shields.io/badge/License-MIT-green?style=for-the-badge)

---

## 📖 Descripción

En la **Semana 9**, TaskBoard pasa de solo mostrar datos a **capturarlos**. Se aprenden los fundamentos de los formularios HTML y se construye el formulario real **"Nueva Transacción"**, que guarda datos con Eloquent. Abarca dos guías:

- **Jueves** — Fundamentos: formulario *sandbox* de práctica, métodos GET vs POST.
- **Viernes** — Formulario real "Nueva Transacción" conectado a la base de datos.

---

## ✨ Características

- ✅ Formulario de práctica (*sandbox*) para experimentar con elementos HTML.
- ✅ Formulario real "Nueva Transacción" que hereda el layout del proyecto.
- ✅ Protección contra CSRF con `@csrf`.
- ✅ Campo oculto `comercio_id` para asociar la transacción a su comercio.
- ✅ Ruta `GET` para mostrar el formulario y ruta `POST` para guardarlo con `Transaccion::create()`.

---

## 🛠️ Tecnologías

| Herramienta | Uso |
|---|---|
| **Laravel 11.x** | Framework principal |
| **Blade** | Formularios y vistas |
| **Eloquent ORM** | Guardar la transacción |
| **MySQL** | Base de datos |

---

## 📋 Requisitos

- PHP **8.2+**, Composer y Laravel instalados
- Proyecto de las Semanas 6–8 funcionando (modelos, relaciones y vistas Blade)

---

## ⚙️ Instalación

```bash
git clone https://github.com/H3CT0R503/NOMBRE-DEL-REPO.git
cd NOMBRE-DEL-REPO
composer install
cp .env.example .env
php artisan key:generate
php artisan migrate
php artisan serve
```

---

## 🕹️ Uso

| Método | Ruta | Nombre | Acción |
|---|---|---|---|
| GET | `/practica/formulario-demo` | — | Formulario sandbox de práctica |
| GET | `/comercios/{comercio}/transacciones/nueva` | `transacciones.create` | Muestra el formulario "Nueva Transacción" |
| POST | `/transacciones` | `transacciones.store` | Guarda la transacción en la base de datos |

> Verifica las rutas con `php artisan route:list`.

---

## 📂 Estructura (relevante)

```text
resources/views/
├── practica/
│   └── formulario_demo.blade.php   # sandbox (jueves)
└── transacciones/
    └── create.blade.php            # formulario "Nueva Transacción" (viernes)

app/Http/Controllers/TransaccionController.php   # métodos create() y store()
```

---

## 🧠 Conceptos aplicados

- **GET vs POST:** GET muestra datos en la URL; POST envía datos de forma oculta.
- **`@csrf`:** token que protege el formulario contra ataques de falsificación de petición.
- **Campo oculto:** llevar el `comercio_id` sin mostrarlo al usuario.
- **Flujo de guardado:** formulario → ruta POST → `store()` → `Transaccion::create()`.

---

## 👤 Autor

**Hector Interiano**
📚 Integración de Sistemas · Ciclo 02-2026
🎓 UPED "Dr. Luis Alonso Aparicio" · Docente: Ing. Oscar Contreras

---

<p align="center">Hecho con 💙 y Laravel</p>

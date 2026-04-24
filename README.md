# 🚀 Clinova - Sistema Laravel

## 📋 Requisitos

* PHP >= 8.x
* Composer
* Node.js + npm
* Docker (recomendado)

---

## ⚙️ Instalación (modo Docker recomendado)

### 1. Clonar repositorio

```bash id="k0xk0p"
git clone <repo-url>
cd clinova
```

---

### 2. Configurar entorno

```bash id="sq4xpt"
cp .env.example .env
```

Configurar base de datos según `docker-compose.yml`

---

### 3. Levantar contenedores

```bash id="l8dj3c"
docker compose up -d --build
```

---

### 4. Instalar dependencias dentro del contenedor

```bash id="3k9z8q"
docker compose exec app composer install
docker compose exec app php artisan key:generate
docker compose exec app php artisan migrate
```

---

### 5. Frontend

```bash id="ru1a9d"
npm install
npm run dev
```

---

## 🌐 Acceso

* App: http://localhost
* (ajustar según puertos en docker-compose)

---

## 🧪 Testing

```bash id="t8jj6c"
docker compose exec app php artisan test
```

---

## 📂 Estructura relevante

* `docker/` → configuración de contenedores
* `app/` → lógica backend
* `resources/` → frontend
* `routes/` → rutas
* `database/` → migraciones
* `storage/` → logs/cache (no versionado)

---

## 🔐 Reglas del equipo

* ❌ No subir `.env`
* ❌ No subir `node_modules`
* ❌ No subir `vendor`
* ❌ No subir `backups`
* ✔️ Usar migraciones siempre
* ✔️ Usar ramas feature

---

## 🔄 Flujo de trabajo

```bash id="2r3y2l"
git checkout -b feature/nueva-funcionalidad
git commit -m "feat: nueva funcionalidad"
git push origin feature/nueva-funcionalidad
```

---

## 🐳 Comandos útiles Docker

```bash id="kp7z7p"
docker compose up -d
docker compose down
docker compose logs -f
docker compose exec app bash
```

---

## 📌 Notas

Si hay errores de permisos:

```bash id="v7qlsf"
chmod -R 775 storage bootstrap/cache
```

# Calculadora de Salarios

Aplicación web para calcular salarios de empleados en función de horas trabajadas, incluyendo manejo de horas extra y almacenamiento en base de datos.

---

## 📌 Características

* Cálculo automático de salario:

  * Horas normales (≤ 40)
  * Horas extra (40–48) con recargo del 20%
  * Horas extra dobles (> 48) con recargo del 40%
* Formulario web para captura de datos
* Persistencia en base de datos MySQL
* Backend en Flask
* Frontend simple en HTML + CSS

---

## 🏗️ Arquitectura

```
project/
│
├── app.py
├── requirements.txt
├── templates/
│   ├── base.html
│   ├── formulario.html
│   └── resultado.html
├── static/
│   ├── styles.css
└── venv/ <- esntorno python venv
```

---

## ⚙️ Requisitos

* Python 3.8+
* MySQL (XAMPP recomendado)
* pip

---

## 📦 Instalación

### 1. Clonar el repositorio

```
git clone https://github.com/ElHackerDaniel/Calculadora-de-Salarios.git
```
```
cd Calculadora-de-Salarios
```

### 2. Crear entorno virtual

```
python -m venv venv
```

### 3. Activar entorno

Windows

`venv\Scripts\activate`

CMD

`venv\Scripts\activate.bat`

Linux / Mac

`source venv/bin/activate`

### 4. Instalar dependencias

```
pip install -r requirements.txt
```

---

## 🗄️ Configuración de Base de Datos

Crear base de datos en MySQL:

```sql
CREATE DATABASE empleados;

USE empleados;

CREATE TABLE empleados (
    id INT AUTO_INCREMENT PRIMARY KEY,
    cedula VARCHAR(20),
    nombre VARCHAR(50),
    apellido VARCHAR(50),
    telefono VARCHAR(20),
    horas INT,
    valor_hora FLOAT,
    salario FLOAT
);
```

Configuración en `app.py`:

```python
db_config = {
    'host': 'localhost',
    'user': 'root',
    'password': '',
    'database': 'empleados'
}
```

---

## ▶️ Ejecución

```
python app.py
```

Acceder en navegador:

```
http://127.0.0.1:5000
```

---

## 🧮 Lógica de Cálculo

* ≤ 40 horas → salario normal
* 41–48 horas → recargo 1.2x
* > 48 horas → recargo 1.4x

---

## 📁 Frontend

* HTML para estructura
* CSS para estilos
* Templates renderizados con Flask (Jinja2)

---

## ⚠️ Consideraciones

* El modo `debug=True` es solo para desarrollo
* No hay validaciones avanzadas de entrada
* Credenciales de base de datos están en texto plano

---

## 🚀 Mejoras futuras

* Validación de formularios
* Autenticación de usuarios
* API REST
* Dockerización
* Deploy en la nube

---

👨‍💻 Autor
----
Proyecto desarrollado como parte del proceso de aprendizaje en desarrollo web Full Stack, enfocado en la construcción de un sistema que calcula el salario, utilizando Python, html, css y sql.

Att: XorSvn

# 🐍 Instalación de Python en Ubuntu desde la Terminal

Este documento explica cómo instalar **Python** en sistemas **Ubuntu** (o distribuciones basadas en Debian) y preparar el entorno para ejecutar programas de Python desde la terminal.

---

## 📋 Requisitos previos

Antes de comenzar, asegúrate de contar con:

- Un sistema **Ubuntu 20.04 o superior** (también funciona en Linux Mint, Pop!_OS, Debian, etc.).
- Permisos de **administrador (sudo)**.
- Conexión a internet activa.

---

## ⚙️ Paso 1. Verificar si Python ya está instalado

Ejecuta en la terminal:

```bash
python3 --version
```

Si aparece algo como `Python 3.x.x`, ya tienes Python instalado y puedes omitir la instalación.  
Si ves un mensaje como “command not found”, continúa con los pasos siguientes.

---

## ⚙️ Paso 2. Actualizar los repositorios

```bash
sudo apt update
sudo apt upgrade -y
```

Esto asegura que los paquetes del sistema estén actualizados antes de instalar Python.

---

## ⚙️ Paso 3. Instalar Python

Ubuntu 20.04 y posteriores suelen incluir Python 3 en los repositorios oficiales.

Para instalarlo:

```bash
sudo apt install python3 -y
```

También puedes instalar herramientas adicionales útiles:

```bash
sudo apt install python3-pip python3-venv -y
```

**Explicación:**
- `python3`: intérprete principal de Python.
- `python3-pip`: gestor de paquetes de Python.
- `python3-venv`: módulo para crear entornos virtuales.

---

## ⚙️ Paso 4. Verificar la instalación

Confirma que Python y pip se instalaron correctamente:

```bash
python3 --version
pip3 --version
```

Deberías ver la versión instalada, por ejemplo:

```
Python 3.12.3
pip 24.0 from /usr/lib/python3/dist-packages/pip (python 3.12)
```

---

## ⚙️ Paso 5. Ejecutar un programa en Python

Crea un archivo de prueba:

```bash
nano hola.py
```

Escribe el siguiente código:

```python
print("¡Hola, mundo desde Python!")
```

Guarda y cierra (Ctrl + O, Enter, Ctrl + X).

Ejecuta el programa:

```bash
python3 hola.py
```

Deberías ver el mensaje:

```
¡Hola, mundo desde Python!
```

---

## ⚙️ Paso 6. Crear un entorno virtual (opcional pero recomendado)

Para proyectos más grandes, es mejor usar entornos virtuales:

```bash
python3 -m venv venv
```

Activa el entorno:

```bash
source venv/bin/activate
```

Tu prompt debería mostrar `(venv)` al inicio.  
Para salir del entorno virtual, ejecuta:

```bash
deactivate
```

---

## 🧰 Comandos útiles

| Acción | Comando |
|--------|----------|
| Ver versión de Python | `python3 --version` |
| Ver versión de pip | `pip3 --version` |
| Instalar un paquete | `pip install nombre_paquete` |
| Listar paquetes instalados | `pip list` |
| Crear entorno virtual | `python3 -m venv venv` |
| Activar entorno virtual | `source venv/bin/activate` |
| Desactivar entorno virtual | `deactivate` |

---

## ✅ Conclusión

Ya tienes **Python** instalado y configurado en Ubuntu.  
Puedes ejecutar programas, instalar librerías con `pip`, y trabajar en entornos virtuales de manera profesional.

---

📚 **Documentación oficial:**  
- [https://www.python.org/downloads/](https://www.python.org/downloads/)  
- [https://docs.python.org/3/using/index.html](https://docs.python.org/3/using/index.html)

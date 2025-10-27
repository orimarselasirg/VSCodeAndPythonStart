# 🧑‍💻 Instalación de Visual Studio Code en Ubuntu desde la Terminal

Este documento te guiará paso a paso para instalar **Visual Studio Code (VS Code)** —un editor de código ligero y potente desarrollado por Microsoft— directamente desde la terminal en **Ubuntu** o cualquier distribución basada en Debian.

---

## 📋 Requisitos previos

Antes de comenzar, asegúrate de tener:

- Un sistema **Ubuntu 20.04 o superior** (también funciona en derivados como Linux Mint o Pop!_OS).
- Acceso a una terminal con permisos de **sudo**.
- Conexión a internet activa.

---

## ⚙️ Instalación paso a paso

### 1. Actualizar los repositorios del sistema

Primero, actualiza la lista de paquetes disponibles y sus versiones:

```bash
sudo apt update
sudo apt upgrade -y
```

---

### 2. Instalar dependencias necesarias

VS Code requiere algunas dependencias básicas que deben estar instaladas:

```bash
sudo apt install software-properties-common apt-transport-https wget -y
```

---

### 3. Importar la clave GPG de Microsoft

Esta clave permite verificar que los paquetes de VS Code provienen de una fuente segura:

```bash
wget -qO- https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > packages.microsoft.gpg
sudo install -o root -g root -m 644 packages.microsoft.gpg /usr/share/keyrings/
```

---

### 4. Agregar el repositorio oficial de Visual Studio Code

Agrega el repositorio de Microsoft a la lista de fuentes de `apt`:

```bash
sudo sh -c 'echo "deb [arch=amd64 signed-by=/usr/share/keyrings/packages.microsoft.gpg] https://packages.microsoft.com/repos/code stable main" > /etc/apt/sources.list.d/vscode.list'
```

---

### 5. Actualizar nuevamente los paquetes

Después de agregar el nuevo repositorio, actualiza los índices de paquetes:

```bash
sudo apt update
```

---

### 6. Instalar Visual Studio Code

Ahora puedes instalar VS Code con:

```bash
sudo apt install code -y
```

---

### 7. Verificar la instalación

Ejecuta el siguiente comando para confirmar que VS Code se instaló correctamente:

```bash
code --version
```

Si ves un número de versión, la instalación fue exitosa.

---

## 🚀 Ejecutar Visual Studio Code

Para abrir VS Code desde la terminal, usa:

```bash
code
```

O bien, abre un proyecto específico:

```bash
code nombre-de-tu-carpeta
```

---

## 🧰 Comandos útiles

| Acción | Comando |
|--------|----------|
| Abrir VS Code | `code` |
| Abrir una carpeta | `code .` |
| Abrir un archivo específico | `code archivo.js` |
| Reinstalar VS Code | `sudo apt install --reinstall code -y` |
| Desinstalar VS Code | `sudo apt remove code -y` |

---

## 🧩 Extensiones recomendadas (opcional)

Puedes instalar extensiones populares desde la terminal, por ejemplo:

```bash
code --install-extension esbenp.prettier-vscode
code --install-extension dbaeumer.vscode-eslint
code --install-extension ms-python.python
```

---

## ✅ Conclusión

Ahora tienes **Visual Studio Code** instalado y configurado correctamente en Ubuntu desde la terminal.  
Puedes iniciar tus proyectos directamente con `code .` y personalizar el entorno según tus necesidades.

---

📚 **Documentación oficial:**  
[https://code.visualstudio.com/docs/setup/linux](https://code.visualstudio.com/docs/setup/linux)

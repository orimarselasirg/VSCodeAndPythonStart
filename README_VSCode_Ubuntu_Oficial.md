# 🧑‍💻 Instalación de Visual Studio Code en Ubuntu (Basado en la documentación oficial)

Este instructivo sigue los pasos oficiales de Microsoft para instalar **Visual Studio Code (VS Code)** en sistemas **Ubuntu** o distribuciones basadas en **Debian**.

📖 Fuente: [Documentación oficial de VS Code](https://code.visualstudio.com/docs/setup/linux)

---

## 📋 Requisitos previos

Antes de comenzar, asegúrate de tener:

- Una distribución basada en Debian o Ubuntu (ej. Ubuntu, Linux Mint, Pop!_OS).
- Acceso a una terminal con permisos de **sudo**.
- Conexión a internet.
- (Opcional) Tener instalado **Snap**, si prefieres usar ese método de instalación.

---

## ⚙️ Método 1: Instalación mediante paquete `.deb` (recomendado)

### 1. Descargar el archivo `.deb`

Descarga el paquete `.deb` más reciente desde el sitio oficial de VS Code:

[https://code.visualstudio.com/download](https://code.visualstudio.com/download)

### 2. Instalar el paquete `.deb`

Navega hasta el directorio donde descargaste el archivo y ejecuta:

```bash
sudo apt install ./<nombre-del-archivo>.deb
```

> 💡 Si tu sistema no reconoce `apt`, también puedes usar:
>
> ```bash
> sudo dpkg -i <nombre-del-archivo>.deb
> sudo apt-get install -f
> ```

Esta instalación agregará automáticamente el **repositorio de Microsoft** y su **clave de firma**, lo que permitirá recibir actualizaciones automáticas.

---

## ⚙️ Método 2: Instalación agregando el repositorio manualmente

Si prefieres agregar manualmente el repositorio oficial, sigue estos pasos:

### 1. Instalar dependencias necesarias

```bash
sudo apt-get install wget gpg -y
```

### 2. Importar la clave GPG de Microsoft

```bash
wget -qO- https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > microsoft.gpg
sudo install -D -o root -g root -m 644 microsoft.gpg /usr/share/keyrings/microsoft.gpg
rm -f microsoft.gpg
```

### 3. Agregar el repositorio de Visual Studio Code

```bash
sudo sh -c 'echo "deb [arch=amd64 signed-by=/usr/share/keyrings/microsoft.gpg] https://packages.microsoft.com/repos/code stable main" > /etc/apt/sources.list.d/vscode.list'
```

### 4. Actualizar los repositorios e instalar VS Code

```bash
sudo apt install apt-transport-https -y
sudo apt update
sudo apt install code -y   # o code-insiders
```

---

## ⚙️ Método 3: Instalación mediante Snap (opcional)

Visual Studio Code también está disponible en la **Snap Store**.

Para instalarlo:

```bash
sudo snap install --classic code
```

> 💡 Para instalar la versión Insider:
>
> ```bash
> sudo snap install --classic code-insiders
> ```

---

## 🚀 Verificar la instalación

Para confirmar que la instalación fue exitosa:

```bash
code --version
```

Si aparece un número de versión, VS Code está correctamente instalado.

---

## 🧰 Comandos útiles

| Acción | Comando |
|--------|----------|
| Abrir VS Code | `code` |
| Abrir la carpeta actual | `code .` |
| Abrir un archivo específico | `code archivo.js` |
| Reinstalar VS Code | `sudo apt install --reinstall code -y` |
| Desinstalar VS Code | `sudo apt remove code -y` |

---

## 🧩 Extensiones recomendadas

Puedes instalar extensiones populares directamente desde la terminal:

```bash
code --install-extension esbenp.prettier-vscode
code --install-extension dbaeumer.vscode-eslint
code --install-extension ms-python.python
```

---

📚 **Referencia oficial:**  
[https://code.visualstudio.com/docs/setup/linux](https://code.visualstudio.com/docs/setup/linux)

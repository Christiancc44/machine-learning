# Usamos la base de Python 3.10 oficial compatible con codespaces
FROM mcr.microsoft.com/devcontainers/python:3.10

# Evitar prompts de usuario durante la instalación
ENV DEBIAN_FRONTEND=noninteractive

# Instalar uv para gestión ultra-rápida
RUN pip install uv

# Configurar el espacio de trabajo
WORKDIR /workspaces/${localWorkspaceFolderBasename}

# Instalaremos las dependencias desde el pyproject.toml
# Esto hace que el contenedor se sincronice con tu archivo de configuración
COPY pyproject.toml uv.lock* ./
RUN uv pip install --system -r pyproject.toml
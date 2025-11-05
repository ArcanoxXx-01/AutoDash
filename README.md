# AutoDash

**Sistema Inteligente para la Generación e Integración Automática de Dashboards en Streamlit**

![License](https://img.shields.io/badge/license-MIT-green)
![Python](https://img.shields.io/badge/python-3.10%2B-blue)
![Streamlit](https://img.shields.io/badge/streamlit-1.x-ff4b4b)
![Status](https://img.shields.io/badge/status-prototype-yellow)

---

## Descripción general

**AutoDash** es un sistema basado en inteligencia artificial capaz de **generar código funcional de dashboards en Streamlit** a partir de **descripciones en lenguaje natural**.  
Además, integra automáticamente el código generado en proyectos (nuevos o existentes) y permite la **previsualización inmediata** del resultado en entornos seguros.

El objetivo de AutoDash es **'democratizar' el desarrollo de dashboards**, permitiendo que tanto usuarios sin experiencia en programación como desarrolladores avanzados puedan crear interfaces interactivas de visualización de datos de forma rápida y eficiente.

---

## Características principales

- **Entrada en lenguaje natural:** el usuario describe el dashboard deseado con sus palabras.  
- **Generación automática de código:** un modelo de lenguaje especialisado genera código funcional de Streamlit (Python).  
- **Integración automática:** el sistema inserta o actualiza archivos dentro de un proyecto Python (nuevo o existente).  
- **Ejecución segura:** los dashboards se ejecutan en entornos controlados (sandbox o docker).  
- **Conectividad extendida mediante MCP:** el sistema puede acceder a bases de datos, servicios o archivos locales bajo consentimiento.  
- **Previsualización instantánea:** permite ver el resultado del dashboard generado sin salir del entorno.  

---

## 🏗️ Arquitectura general (Propensa a cambios)

```text
      ┌───────────────┐
      │  User Prompt  │
      └────────┬──────┘
               │
               ▼
      ┌───────────────┐
      │ LLM Generator │ ← Modelos de lenguaje (GPT / local)
      └───────────────┘
               │
               ▼
      ┌───────────────────┐
      │ Code Integration  │ ← Inserta y modifica archivos del proyecto
      └───────────────────┘
               │
               ▼
      ┌────────────────────┐
      │ Preview & Sandbox  │ ← Ejecuta el dashboard de forma segura
      └────────────────────┘
               │
               ▼
      ┌────────────────┐
      │ MCP Connector  │ ← Interactúa con datos, APIs o archivos
      └────────────────┘
```

---

## Instalación y uso

### 1️⃣ Requisitos previos

- Python **3.10 o superior**
- [Streamlit](https://streamlit.io/)
- [Docker](https://www.docker.com/) *(opcional para sandboxing)*
- Clave de API del modelo de lenguaje (por ejemplo, OpenAI)

### 2️⃣ Clonar el repositorio

```bash
git clone https://github.com/ArcanoxXx-01/AutoDash.git
cd AutoDash
```

### 3️⃣ Instalar dependencias

```bash
pip install -r requirements.txt
```

### 4️⃣ Ejecutar el sistema

```bash
python main.py
```

### 5️⃣ Generar un dashboard

Ejemplo de prompt:

```text
Crea un dashboard en Streamlit que cargue un CSV llamado ventas.csv,
muestre una tabla interactiva y un gráfico de barras con las ventas por categoría.
```

---

## Tecnologías y componentes

| Componente | Tecnología / Librería |
|-------------|-----------------------|
| Generación de código | Modelos de Lenguaje (LLM: GPT, Claude, etc.) |
| Framework de visualización | Streamlit |
| Integración automática | Análisis de AST y manipulación de archivos |
| Ejecución segura | Docker + entorno sandbox |
| Extensiones / I/O | MCP |
| Lenguaje principal | Python 3.10+ |

---

## Ejemplo de uso (en desarrollo)

```python
from autodash import AutoDash

app = AutoDash()
app.prompt("Crea un dashboard con gráfico de líneas del archivo data.csv")
app.preview()
```

---

## Estado actual del proyecto

| Módulo | Estado |
|---------|--------|
| Generador de código | Etapa investigativa |
| Integrador de código | Etapa investigativa |
| Módulo MCP | Etapa investigativa |
| Sandbox / Preview | Etapa investigativa |
| UI / Interfaz web | Etapa investigativa |

---

## 📚 Créditos y licencia

Desarrollado por **Darío López Falcón** como parte de un proyecto de tesis en Ciencias de la Computación (2025).  
Licenciado bajo los términos de la [MIT License](./LICENSE).

---

## 🤝 Contribuciones

¡Las contribuciones son bienvenidas!  
Puedes abrir issues o enviar pull requests con mejoras o nuevas ideas para la arquitectura.

---

## 🌐 Contacto

- **Autor:** Darío López Falcón  
- **Email:** dariolf03@gmail.com

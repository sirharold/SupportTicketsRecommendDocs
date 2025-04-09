# Weaviate Data Loader

Este proyecto carga preguntas/respuestas y artículos técnicos en un cluster de **Weaviate Cloud Service**, usando el cliente oficial de Python.

---

## 🧾 Requisitos

- Cuenta en [Weaviate Cloud](https://console.weaviate.cloud)
- API Key de Weaviate
- API Key de OpenAI
- Python 3.8+
- Archivos:
  - `questions_data.json`
  - `azure_docs_full.json`
  - `.env` con tus claves (ver `.env.example`)

---

## 🛠 Instalación

```bash
pip install -r requirements.txt
```

---

## ⚙️ Uso

1. Crea tu archivo `.env` a partir de `.env.example`
2. Coloca los archivos de datos en el mismo directorio
3. Ejecuta el notebook `Weaviate Data Loader`

---

## 🔁 Características

- ✅ Control de reprocesamiento con archivos de seguimiento (`qa_uploaded_ids.txt`, `docs_uploaded_links.txt`)
- 🛑 Logging automático en `weaviate_errors.log`
- 📉 Indicadores de avance con `tqdm`
- 🧱 Crea esquemas solo si no existen
- 🧪 Validación mínima de campos obligatorios por registro

---

## 📂 Estructura esperada

### QnA

| Campo            | Tipo     |
|------------------|----------|
| title            | text     |
| question_content | text     |
| accepted_answer  | text     |
| url              | text     |
| tags             | text[]   |
| date             | date     |

### Documentation

| Campo         | Tipo     |
|---------------|----------|
| title         | text     |
| summary       | text     |
| content       | text     |
| link          | text     |
| related_links | text[]   |

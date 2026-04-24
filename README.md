# NotaFiscal Generator

<div align="center">

![version](https://img.shields.io/badge/version-5.0-f0b429?style=flat-square)
![SEFAZ](https://img.shields.io/badge/SEFAZ-v4.00-58a6ff?style=flat-square)
![license](https://img.shields.io/badge/license-MIT-3fb950?style=flat-square)
![no server](https://img.shields.io/badge/no%20server-browser%20only-bc8cff?style=flat-square)

**Gerador de XML NF-e em lote · Generador XML NF-e por lotes · NF-e XML Batch Generator**

[🇪🇸 Español](#-español) · [🇬🇧 English](#-english) · [🇧🇷 Português](#-português)

</div>

---

## 🇪🇸 Español

### ¿Qué es?

Herramienta web que genera ficheros XML de **Nota Fiscal Eletrônica (NF-e) brasileña v4.00** en lote, a partir de una plantilla XML real y un CSV con los datos variables. Funciona completamente en el navegador, sin servidor ni instalación.

> ⚠️ Los XML generados tienen **firma digital inválida** (la de la plantilla original). Son válidos para pruebas internas — **no** para envío a SEFAZ en producción.

### Características

- 📥 **Modo Receptor** — tus datos como destinatario son fijos; los emisores (proveedores) varían por CSV
- 📤 **Modo Emisor** — tus datos como emitente son fijos; los destinatarios (clientes) varían por CSV
- ✏️ **Datos fijos editables** — extrae los datos de la plantilla y permite modificarlos antes de generar
- 📂 **Upload de CSV** — sube un fichero `.csv` o pega los datos directamente
- 📦 **Descarga en ZIP** — descarga todos los XML generados de una vez
- 🌍 **Multiidioma** — Español, English, Português
- ❓ **Guía integrada** — ayuda en el idioma activo dentro de la propia app
- 🔢 **Chave de acesso correcta** — algoritmo mod-11 SEFAZ oficial
- 🧮 **Cálculos automáticos** — ICMS, IPI (CST 00/70), nProt incremental, nFat, duplicatas

### Uso rápido

1. Abre `nfe_generator_v5.html` en cualquier navegador moderno
2. Elige el modo (Receptor / Emisor)
3. Carga tu plantilla XML real (drag & drop)
4. Verifica/edita tus datos fijos
5. Sube o pega el CSV con los datos variables
6. Pulsa ⚡ Generar XML → descarga individual o ZIP

### Estructura del repositorio

```
nfe-batch-generator/
├── nfe_generator_v5.html   # Aplicación completa (un solo fichero)
├── nfe_generator_guide.md  # Guía de usuario trilingüe
└── README.md
```

---

## 🇬🇧 English

### What is it?

A web tool that generates **Brazilian NF-e XML files (v4.00)** in batch, from a real XML template and a CSV file with variable data. Runs entirely in the browser — no server or installation required.

> ⚠️ Generated XMLs have an **invalid digital signature** (from the original template). Valid for internal testing only — **not** for submission to SEFAZ in production.

### Features

- 📥 **Recipient mode** — your data as recipient is fixed; issuers (suppliers) vary per CSV row
- 📤 **Issuer mode** — your data as issuer is fixed; recipients (customers) vary per CSV row
- ✏️ **Editable fixed data** — extracts data from the template and lets you modify it before generating
- 📂 **CSV upload** — upload a `.csv` file or paste data directly
- 📦 **ZIP download** — download all generated XMLs at once
- 🌍 **Multilanguage** — Español, English, Português
- ❓ **Built-in guide** — contextual help in the active language
- 🔢 **Correct access key** — official SEFAZ mod-11 algorithm
- 🧮 **Automatic calculations** — ICMS, IPI (CST 00/70), incremental nProt, nFat, duplicatas

### Quick start

1. Open `nfe_generator_v5.html` in any modern browser
2. Choose the mode (Recipient / Issuer)
3. Load your real XML template (drag & drop)
4. Review/edit your fixed data
5. Upload or paste the CSV with variable data
6. Click ⚡ Generate XML → download individually or as ZIP

### Repository structure

```
nfe-batch-generator/
├── nfe_generator_v5.html   # Full application (single file)
├── nfe_generator_guide.md  # Trilingual user guide
└── README.md
```

---

## 🇧🇷 Português

### O que é?

Uma ferramenta web que gera arquivos XML de **Nota Fiscal Eletrônica (NF-e) v4.00** em lote, a partir de um modelo XML real e um CSV com os dados variáveis. Funciona completamente no navegador, sem servidor ou instalação.

> ⚠️ Os XMLs gerados possuem **assinatura digital inválida** (a do modelo original). Válidos apenas para testes internos — **não** para envio à SEFAZ em produção.

### Funcionalidades

- 📥 **Modo Receptor** — seus dados como destinatário são fixos; os emitentes (fornecedores) variam por CSV
- 📤 **Modo Emissor** — seus dados como emitente são fixos; os destinatários (clientes) variam por CSV
- ✏️ **Dados fixos editáveis** — extrai os dados do modelo e permite modificá-los antes de gerar
- 📂 **Upload de CSV** — carregue um arquivo `.csv` ou cole os dados diretamente
- 📦 **Download em ZIP** — baixe todos os XMLs gerados de uma vez
- 🌍 **Multilíngue** — Español, English, Português
- ❓ **Guia integrado** — ajuda contextual no idioma ativo
- 🔢 **Chave de acesso correta** — algoritmo mod-11 SEFAZ oficial
- 🧮 **Cálculos automáticos** — ICMS, IPI (CST 00/70), nProt incremental, nFat, duplicatas

### Início rápido

1. Abra `nfe_generator_v5.html` em qualquer navegador moderno
2. Escolha o modo (Receptor / Emissor)
3. Carregue seu modelo XML real (arraste e solte)
4. Verifique/edite seus dados fixos
5. Carregue ou cole o CSV com os dados variáveis
6. Clique em ⚡ Gerar XML → baixe individualmente ou em ZIP

### Estrutura do repositório

```
nfe-batch-generator/
├── nfe_generator_v5.html   # Aplicação completa (arquivo único)
├── nfe_generator_guide.md  # Guia do usuário trilíngue
└── README.md
```

---

## Columnas CSV / CSV Columns / Colunas CSV

### Modo Receptor / Recipient mode / Modo Receptor

```
nNF,xPed,CNPJ_emit,xNome_emit,IE_emit,CRT,xLgr_emit,nro_emit,xBairro_emit,xMun_emit,UF_emit,CEP_emit,qCom,uCom,vUnCom,vProd,vNF,xProd,NCM,CST_IPI,pIPI,pICMS_row
```

### Modo Emisor / Issuer mode / Modo Emissor

```
nNF,xPed,CNPJ_dest,xNome_dest,IE_dest,xLgr_dest,nro_dest,xBairro_dest,xMun_dest,UF_dest,CEP_dest,qCom,uCom,vUnCom,vProd,vNF,xProd,NCM,CST_IPI,pIPI,pICMS_row
```

---

## License

MIT — free to use and modify.

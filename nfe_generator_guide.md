# NF-e Batch Generator v5

---

## 🇪🇸 Guía de usuario — Español

### ¿Qué hace esta herramienta?

Genera ficheros XML de Nota Fiscal Eletrônica (NF-e) brasileña v4.00 en lote, a partir de una plantilla XML real y un CSV con los datos variables. Funciona completamente en el navegador, sin servidor ni instalación.

> ⚠️ Los XML generados tienen **firma digital inválida** (la de la plantilla original). Son válidos para pruebas internas, no para envío a SEFAZ en producción.

---

### Modos de operación

| Modo | Descripción |
|---|---|
| 📥 **Receptor** | Eres el destinatario (`dest`) de las notas. Tus datos son fijos. Los datos del **emisor** (proveedor) varían por fila en el CSV. |
| 📤 **Emisor** | Eres el emitente (`emit`) de las notas. Tus datos son fijos. Los datos del **destinatario** (cliente) varían por fila en el CSV. |

---

### Paso a paso

1. **Elige el idioma** con las banderas del header (🇪🇸 🇬🇧 🇧🇷).
2. **Elige el modo** — Receptor o Emisor — con el selector del header.
3. **Carga la plantilla XML**: arrastra un fichero NF-e real o haz clic en la zona punteada. Los datos fijos se extraen automáticamente.
4. **Verifica y edita** tus datos fijos en el panel derecho. Los campos modificados se marcan en morado. Usa **↺ Reset** para restaurar los valores originales.
5. **Prepara el CSV** con los datos variables. Usa "📂 Subir CSV" o pega directamente en el área de texto. Pulsa **Ejemplo** para ver el formato correcto.
6. **Configura** pICMS default, tpAmb y (opcionalmente) nProt base y dhEmi override.
7. **Genera** pulsando ⚡ Generar XML. Descarga cada fichero individualmente o todos juntos en ZIP.

---

### Columnas CSV — Modo Receptor

| Columna | Descripción | Ejemplo |
|---|---|---|
| `nNF` | Número de la nota | `77012` |
| `xPed` | Número de pedido | `7100008812` |
| `CNPJ_emit` | CNPJ del emisor (14 dígitos, sin puntos) | `02668458000149` |
| `xNome_emit` | Razão Social del emisor | `DOMICILI IND E COM` |
| `IE_emit` | Inscrição Estadual | `336695410116` |
| `CRT` | Régimen tributario (1=Simples, 3=Lucro) | `1` |
| `xLgr_emit` | Calle | `RUA JOSE CAMPANELLA` |
| `nro_emit` | Número | `380` |
| `xBairro_emit` | Barrio | `MACEDO` |
| `xMun_emit` | Municipio | `GUARULHOS` |
| `UF_emit` | Estado (sigla) | `SP` |
| `CEP_emit` | CEP (8 dígitos, sin guión) | `07112100` |
| `qCom` | Cantidad (4 decimales) | `3.0000` |
| `uCom` | Unidad de medida | `UN` |
| `vUnCom` | Precio unitario | `450.00` |
| `vProd` | Total ítem (qCom × vUnCom) | `1350.00` |
| `vNF` | Total nota | `1646.34` |
| `xProd` | Descripción del producto | `FPO-16.1 BR` |
| `NCM` | Código NCM | `73182200` |
| `CST_IPI` | 00=tributado, 70=exento | `70` |
| `pIPI` | Alícuota IPI % | `0.00` |
| `pICMS_row` | % ICMS este ítem (vacío = default global) | `18.00` |

En **Modo Emisor** las columnas del emisor se reemplazan por las del destinatario: `CNPJ_dest`, `xNome_dest`, `IE_dest`, `xLgr_dest`, `nro_dest`, `xBairro_dest`, `xMun_dest`, `UF_dest`, `CEP_dest`.

---

### Errores frecuentes

- **CNPJ inválido**: debe tener exactamente 14 dígitos numéricos, sin puntos ni guiones.
- **CEP inválido**: 8 dígitos sin guión. Ej: `07112100`
- **vNF inválido**: usa punto como separador decimal, no coma.
- **vUnCom ≠ vProd/qCom**: verifica que precio unitario × cantidad = total ítem.

---
---

## 🇬🇧 User Guide — English

### What does this tool do?

Generates Brazilian NF-e XML files (v4.00) in batch, from a real XML template and a CSV file with variable data. Runs entirely in the browser — no server or installation required.

> ⚠️ Generated XMLs have an **invalid digital signature** (from the original template). They are valid for internal testing only, not for submission to SEFAZ in production.

---

### Operation modes

| Mode | Description |
|---|---|
| 📥 **Recipient** | You are the recipient (`dest`) of the invoices. Your data is fixed. The **issuer** (supplier) data varies per CSV row. |
| 📤 **Issuer** | You are the issuer (`emit`) of the invoices. Your data is fixed. The **recipient** (customer) data varies per CSV row. |

---

### Step by step

1. **Choose the language** using the flag buttons in the header (🇪🇸 🇬🇧 🇧🇷).
2. **Choose the mode** — Recipient or Issuer — using the header selector.
3. **Load the XML template**: drag a real NF-e file or click the dotted area. Fixed data is extracted automatically.
4. **Review and edit** your fixed data in the right panel. Modified fields are highlighted in purple. Use **↺ Reset** to restore original values.
5. **Prepare the CSV** with variable data. Use "📂 Upload CSV" or paste directly into the text area. Click **Example** to see the correct format.
6. **Configure** default pICMS, tpAmb, and optionally nProt base and dhEmi override.
7. **Generate** by clicking ⚡ Generate XML. Download files individually or all together as a ZIP.

---

### CSV columns — Recipient mode

| Column | Description | Example |
|---|---|---|
| `nNF` | Invoice number | `77012` |
| `xPed` | Purchase order number | `7100008812` |
| `CNPJ_emit` | Issuer CNPJ (14 digits, no dots) | `02668458000149` |
| `xNome_emit` | Issuer company name | `DOMICILI IND E COM` |
| `IE_emit` | State Tax ID | `336695410116` |
| `CRT` | Tax regime (1=Simples, 3=Lucro) | `1` |
| `xLgr_emit` | Street name | `RUA JOSE CAMPANELLA` |
| `nro_emit` | Street number | `380` |
| `xBairro_emit` | District | `MACEDO` |
| `xMun_emit` | City | `GUARULHOS` |
| `UF_emit` | State code | `SP` |
| `CEP_emit` | ZIP code (8 digits, no dash) | `07112100` |
| `qCom` | Quantity (4 decimals) | `3.0000` |
| `uCom` | Unit of measure | `UN` |
| `vUnCom` | Unit price | `450.00` |
| `vProd` | Item total (qCom × vUnCom) | `1350.00` |
| `vNF` | Invoice total | `1646.34` |
| `xProd` | Product description | `FPO-16.1 BR` |
| `NCM` | NCM code | `73182200` |
| `CST_IPI` | 00=taxed, 70=exempt | `70` |
| `pIPI` | IPI rate % | `0.00` |
| `pICMS_row` | ICMS % for this row (empty = global default) | `18.00` |

In **Issuer mode**, issuer columns are replaced by recipient columns: `CNPJ_dest`, `xNome_dest`, `IE_dest`, `xLgr_dest`, `nro_dest`, `xBairro_dest`, `xMun_dest`, `UF_dest`, `CEP_dest`.

---

### Common errors

- **Invalid CNPJ**: must be exactly 14 numeric digits, no dots or dashes.
- **Invalid CEP**: 8 digits, no dash. E.g.: `07112100`
- **Invalid vNF**: use a dot as decimal separator, not a comma.
- **vUnCom ≠ vProd/qCom**: verify that unit price × quantity = item total.

---
---

## 🇧🇷 Guia do Usuário — Português

### O que esta ferramenta faz?

Gera arquivos XML de Nota Fiscal Eletrônica (NF-e) brasileira v4.00 em lote, a partir de um modelo XML real e um CSV com os dados variáveis. Funciona completamente no navegador, sem servidor ou instalação.

> ⚠️ Os XMLs gerados possuem **assinatura digital inválida** (a do modelo original). São válidos para testes internos, não para envio à SEFAZ em produção.

---

### Modos de operação

| Modo | Descrição |
|---|---|
| 📥 **Receptor** | Você é o destinatário (`dest`) das notas. Seus dados são fixos. Os dados do **emitente** (fornecedor) variam por linha no CSV. |
| 📤 **Emissor** | Você é o emitente (`emit`) das notas. Seus dados são fixos. Os dados do **destinatário** (cliente) variam por linha no CSV. |

---

### Passo a passo

1. **Escolha o idioma** usando as bandeiras no cabeçalho (🇪🇸 🇬🇧 🇧🇷).
2. **Escolha o modo** — Receptor ou Emissor — com o seletor no cabeçalho.
3. **Carregue o modelo XML**: arraste um arquivo NF-e real ou clique na área pontilhada. Os dados fixos são extraídos automaticamente.
4. **Verifique e edite** seus dados fixos no painel direito. Campos modificados ficam marcados em roxo. Use **↺ Restaurar** para voltar aos valores originais.
5. **Prepare o CSV** com os dados variáveis. Use "📂 Carregar CSV" ou cole diretamente na área de texto. Clique em **Exemplo** para ver o formato correto.
6. **Configure** pICMS padrão, tpAmb e, opcionalmente, nProt base e dhEmi override.
7. **Gere** clicando em ⚡ Gerar XML. Baixe cada arquivo individualmente ou todos juntos em ZIP.

---

### Colunas CSV — Modo Receptor

| Coluna | Descrição | Exemplo |
|---|---|---|
| `nNF` | Número da nota | `77012` |
| `xPed` | Número do pedido | `7100008812` |
| `CNPJ_emit` | CNPJ do emitente (14 dígitos, sem pontos) | `02668458000149` |
| `xNome_emit` | Razão Social do emitente | `DOMICILI IND E COM` |
| `IE_emit` | Inscrição Estadual | `336695410116` |
| `CRT` | Regime tributário (1=Simples, 3=Lucro) | `1` |
| `xLgr_emit` | Logradouro | `RUA JOSE CAMPANELLA` |
| `nro_emit` | Número | `380` |
| `xBairro_emit` | Bairro | `MACEDO` |
| `xMun_emit` | Município | `GUARULHOS` |
| `UF_emit` | Estado (sigla) | `SP` |
| `CEP_emit` | CEP (8 dígitos, sem traço) | `07112100` |
| `qCom` | Quantidade (4 decimais) | `3.0000` |
| `uCom` | Unidade de medida | `UN` |
| `vUnCom` | Preço unitário | `450.00` |
| `vProd` | Total do item (qCom × vUnCom) | `1350.00` |
| `vNF` | Total da nota | `1646.34` |
| `xProd` | Descrição do produto | `FPO-16.1 BR` |
| `NCM` | Código NCM | `73182200` |
| `CST_IPI` | 00=tributado, 70=isento | `70` |
| `pIPI` | Alíquota IPI % | `0.00` |
| `pICMS_row` | % ICMS desta linha (vazio = padrão global) | `18.00` |

No **Modo Emissor** as colunas do emitente são substituídas pelas do destinatário: `CNPJ_dest`, `xNome_dest`, `IE_dest`, `xLgr_dest`, `nro_dest`, `xBairro_dest`, `xMun_dest`, `UF_dest`, `CEP_dest`.

---

### Erros frequentes

- **CNPJ inválido**: deve ter exatamente 14 dígitos numéricos, sem pontos ou traços.
- **CEP inválido**: 8 dígitos sem traço. Ex: `07112100`
- **vNF inválido**: use ponto como separador decimal, não vírgula.
- **vUnCom ≠ vProd/qCom**: verifique que preço unitário × quantidade = total do item.

# teseo-10_envidia-en-el-aula
# TES-10.2: Teseo | Agente de Auditoría y Benchmarking para Investigación Cualitativa

> **"Nullius in verba"** (En palabras de nadie) - *Lema de la Royal Society*

## 🏛️ Contexto y Propósito
**Teseo (TES-10.1)** es un agente de **auditoría forense y adversarial** diseñado para operar en tándem con [Ariadna (ARI-04.3)](https://github.com/victorfaccio-ed/ari-04-11_envidia-en-el-aula).

Mientras Ariadna se enfoca en la interpretación hermenéutica y la conexión de ideas bajo un marco de *pensamiento complejo*, Teseo actúa bajo principios de **Racionalismo Crítico**. Su función no es generar nuevas ideas, sino someter los hallazgos de Ariadna a pruebas de estrés para validar:
1.  **Integridad de Datos:** Detección de alucinaciones (citas inexistentes).
2.  **Consistencia Teórica:** Verificación de alineación estricta con el Codebook (ej. *Envidia en el Aula*).
3.  **Lógica Interna:** Identificación de sesgos interpretativos o saltos lógicos no justificados.

Este sistema "Actor-Crítico" (Red Teaming) eleva la validez metodológica de la investigación asistida por IA.

## ⚙️ Configuración Técnica (JSON)
El núcleo de Teseo reside en el archivo `teseo_config.json`. Este archivo contiene las directivas "Anti-Alucinación" y los protocolos de "Benchmarking".

### Cómo utilizar a Teseo:
1.  **Carga del Contexto:** Sube tus datos crudos (entrevistas, textos) al modelo de IA.
2.  **Inyección del Prompt:** Copia el contenido de `teseo_config.json` como instrucción del sistema.
3.  **Input de Auditoría:** Pega el reporte generado previamente por Ariadna.
4.  **Ejecución:** Teseo generará un reporte de aprobación o rechazo de los hallazgos.

## 🛡️ Protocolos de Auditoría (Las 3 Capas)

### Capa 1: Verdad Fáctica (Anti-Hallucination)
Teseo escanea cada texto entrecomillado en el reporte de Ariadna y busca su coincidencia exacta (`verbatim`) en los archivos fuente.
* ✅ **Pasa:** La cita existe y es precisa.
* ❌ **Falla:** La cita está alterada o inventada.

### Capa 2: Alineación Teórica (Codebook Check)
Verifica si las categorías aplicadas (ej. `ENV-NUTRITIVA`, `VIOL-SIMBOLICA`) cumplen con las definiciones operacionales del marco teórico.
* *Ejemplo:* Si Ariadna etiqueta una acción como "Envidia Nutritiva" pero el texto muestra hostilidad, Teseo marcará un **Error de Clasificación**.

### Capa 3: Prueba de Estrés (Adversarial Logic)
Teseo intenta generar contra-hipótesis para desafiar las interpretaciones subjetivas.
* *Prompt Interno:* "¿Existe una explicación más simple para este fenómeno que la propuesta por Ariadna?"

## 📊 Estructura del Reporte de Auditoría
Los outputs de Teseo siguen el formato estandarizado disponible en `templates/reporte_auditoria.md`:

```text
## 🛡️ Reporte de Auditoría TES-01
**Estado:** ⚠️ REVISIÓN REQUERIDA

**1. Verificación de Citas:**
- [x] Cita A (Validada)
- [ ] Cita B (NO ENCONTRADA - Posible alucinación)

**2. Semáforo Teórico:**
- 🔴 Categoría X: Mal aplicada (Evidencia insuficiente).
- 🟢 Categoría Y: Sólida.

**3. Recomendación:**
- Revisar la interpretación del párrafo 3.

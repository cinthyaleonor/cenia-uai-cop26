# Agent Skills — estándar de calidad (Feedback Docente G11)

Este directorio contiene **skills de especialización** para el caso de uso CENIA *feedback en dinámicas auténticas*.  
Una skill Nivel 3 **no solo ejecuta una tarea**: sabe **cómo hacerla bien**, **por qué** y **cómo verificar** la calidad del resultado.

> Objetivo: transferir **conocimiento experto verificable** a un agente, no acumular prompts largos.

**Caso de uso CENIA** (práctica documentada) ≠ **skill** (criterio experto encapsulado).  
Ver: [`../docs/caso-de-uso-cenia.md`](../docs/caso-de-uso-cenia.md).

---

## Inventario y madurez actual

| Archivo | Dominio | Dinámica | Versión | Nivel declarado | Estado |
| --- | --- | --- | --- | --- | --- |
| [`alegato-derecho.skill.md`](alegato-derecho.skill.md) | Derecho | Alegato oral | 0.2.0 | 3 | Protocolo + evidencia + control jurídico + QA del feedback |
| [`pitch-negocios.skill.md`](pitch-negocios.skill.md) | Negocios / innovación | Pitch / avance | 0.2.0 | 3 | Protocolo + evidencia + control de datos + QA del feedback |

### Autoevaluación rápida (rúbrica institucional)

| Dimensión (peso) | Alegato | Pitch |
| --- | --- | --- |
| Fundamentación disciplinar (20%) | Alta | Alta |
| Rigor metodológico / protocolo (20%) | Alta | Alta |
| Criterios de decisión (15%) | Alta | Alta |
| Validación / evidencia (20%) | Alta | Alta |
| Excepciones / incertidumbre (10%) | Alta | Alta |
| Evaluación reproducible / casos (15%) | Media* | Media* |

\*Los **casos de prueba** están plantillados; falta completarlos con docentes (evidencia empírica de Nivel 3 “cerrado”).

**Umbral Nivel 3 certificado:** ≥ 80% **y** casos de prueba reales donde sin la skill baja la calidad del feedback.

---

## Tres niveles de madurez

| Nivel | Capacidad | Ejemplo (evaluaciones) |
| --- | --- | --- |
| **1. Asistencia** | Ayuda puntual | Genera preguntas. |
| **2. Productividad** | Flujo operativo completo | Armar evaluación + rúbrica. |
| **3. Especialización** | Criterio + método + validación | Diseña, fundamenta y valida con alineamiento constructivo, Bloom, autenticidad, validez/confiabilidad. |

Nivel 3 **no** se gana por extensión del texto: se gana si el conocimiento experto **cambia el resultado**.

---

## Estructura obligatoria de una skill en este repo (alineada a v0.2)

Toda skill de feedback oral debe incluir, en este orden conceptual:

### Capa 1 — Conocimiento
- Frontmatter (`name`, `nivel_skill`, `disciplina`, `version`, `responsable_experto`, …)
- Rol y límites (HITL, sin nota)
- Criterios disciplinares + evidencias buenas/débiles (anclas)
- Distinción dual del dominio (p. ej. jurídico vs argumentativo; storytelling vs descubrimiento)

### Capa 2 — Ejecución
- Arquitectura de análisis (flujo entrada → pasos → salida)
- **Protocolo de análisis** numerado (cómo razonar, no solo qué mirar)
- Salida esperada fija (`Fortalezas` / `Brechas` / `Acciones` / `Pregunta` / `Notas docente`)

### Capa 3 — Aseguramiento de calidad
- **Reglas de evidencia** (explícita / parcial / sin evidencia observable)
- Control de dominio (jurídico / datos de mercado / etc.)
- **Control de calidad del feedback** (checklist pre-entrega)
- Prohibiciones
- Casos de prueba + indicadores + próximo salto

### Seis componentes Nivel 3 (mapa)

| Componente | Dónde se ve en el archivo |
| --- | --- |
| 1. Conocimiento experto | Rol, criterios, anclas, dualidad disciplinar |
| 2. Metodología explícita | Protocolo + arquitectura de análisis |
| 3. Criterios disciplinares | Sección criterios + evidencias |
| 4. Validación | Escala de evidencia + control de fuentes/datos |
| 5. Razonamiento especializado | Protocolo, excepciones, “revisión docente” |
| 6. Mejora continua | Casos de prueba, indicadores, version |

---

## Escala de evidencia (común a todas las skills de feedback)

| Categoría | Significado |
| --- | --- |
| Evidencia explícita | Se observa directamente en la transcripción. |
| Evidencia parcial | Aparece incompleto o poco desarrollado. |
| Sin evidencia observable | No se puede juzgar esa competencia; **declararlo**. |

Regla de oro: preferible “sin evidencia observable” a inventar desempeño.

---

## Plantilla mínima (copiar al crear una skill nueva)

```markdown
---
name: feedback-<dominio>-<dinamica>
nivel_skill: 3
curso: ...
dinamica: ...
disciplina: ...
nivel: pregrado | postgrado
idioma: es
responsable_experto: ...
version: 0.1.0
---

# Rol
...

# Arquitectura de análisis (flujo)
...

# Protocolo de análisis
1. ...

# Reglas de evidencia
| Categoría | Significado |
| Evidencia explícita | ... |
| Evidencia parcial | ... |
| Sin evidencia observable | ... |

# Distinción crítica: <dimensión A> vs <dimensión B>
...

# Control de <dominio> (fuentes / datos / …)
...

# Criterios disciplinares (rúbrica)
## ...

# Evidencias buenas / débiles
...

# Prohibiciones
...

# Control de calidad del feedback (antes de entregar)
1. ...

# Salida esperada
## Fortalezas
## Brechas
## Acciones
## Pregunta de reflexión
## Notas para el docente

# Evaluación y mejora continua
## Casos de prueba
## Indicadores
## Próximo salto
```

---

## Checklist de publicación (gate de calidad)

Antes de mergear o usar en demo/piloto:

- [ ] Frontmatter completo (`nivel_skill`, `version`, `responsable_experto`)
- [ ] Protocolo de análisis **explícito** (no solo lista de criterios)
- [ ] Escala de evidencia en tres categorías
- [ ] Distinción dual del dominio (dos ejes que pueden divergir)
- [ ] Control anti-alucinación propio del dominio
- [ ] Checklist de calidad del **propio** feedback
- [ ] Salida fija compatible con el prototipo (Fortalezas / Brechas / Acciones / Pregunta)
- [ ] ≥ 3 casos de prueba con resultado esperado
- [ ] HITL: sin nota automática
- [ ] Un colega de la disciplina reconocería el estándar

Si falta el protocolo, la escala de evidencia o el control de calidad del feedback → **no** declarar Nivel 3.

---

## Relación con el prototipo

```text
Transcripción → RAG sobre skills/*.skill.md → borrador (LLM u offline)
                                              → docente aprueba (HITL)
```

La skill es el **activo pedagógico**. El modelo solo redacta; el criterio vive aquí.

---

## Ficha de madurez institucional (sugerida CENIA / UAI)

| Campo | Uso |
| --- | --- |
| Nombre / versión | Identificador estable |
| Nivel 1–3 | Según rúbrica + evidencia |
| Disciplina / unidad | Facultad |
| Responsable experto | Aval disciplinar |
| Evidencia de desempeño | Casos + métricas de edición docente |
| Fecha de revisión | Ciclo de mejora |

Ambición: **estándar de certificación de Agent Skills**, no una carpeta de prompts.

---

## Cómo contribuir

1. Copia la plantilla o parte de `alegato-derecho` / `pitch-negocios`.  
2. Completa casos de prueba con el/la docente responsable.  
3. Actualiza la tabla **Inventario y madurez** de este README.  
4. Si hay demo estática, sincroniza también `apps/web/public/skills/` (versión corta o completa).

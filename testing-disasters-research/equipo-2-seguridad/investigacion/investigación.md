# Investigación del Equipo – Ciberseguridad y Fallos en Aplicaciones Web

Esta investigación presenta tres casos emblemáticos relacionados con fallas de seguridad, vulnerabilidades ampliamente explotadas y errores de validación que han afectado a millones de usuarios alrededor del mundo.  
Incluye tablas, análisis técnico, causas, consecuencias y pruebas que habrían prevenido los incidentes.

---

#  Caso 1 — Equifax (Estados Unidos, 2017)

## Resumen del incidente

| Año | Empresa | Descripción | Afectados | Tipo de falla |
|-----|---------|-------------|-----------|----------------|
| 2017 | Equifax (EE. UU.) | Un exploit en la vulnerabilidad **Apache Struts CVE-2017-5638** permitió a atacantes acceder a los servidores de Equifax y extraer datos sensibles de millones de usuarios durante meses. | +147 millones de personas | Vulnerabilidad sin parchear, falta de pruebas y monitoreo |

---

## ¿Qué salió mal?

### **Contexto**
Equifax es una de las agencias de crédito más grandes del mundo. En marzo de 2017 se liberó un parche crítico para Apache Struts que corregía una vulnerabilidad de ejecución remota de código (RCE).  
El equipo de seguridad notificó internamente la necesidad de actualizar… pero el parche **nunca se aplicó** en uno de los servidores públicos.

### **Causas principales**
-  No se aplicó un parche crítico de seguridad.  
-  No existía un inventario actualizado de sistemas vulnerables.  
-  Falta de pruebas de seguridad automatizadas que detectaran la falla.  
-  La vulnerabilidad permitió **ejecución remota de comandos** y acceso persistente.  
-  La intrusión duró **76 días sin ser detectada**.

### **Consecuencias**
-  **147 millones de personas afectadas** (datos personales, SSN, direcciones, tarjetas).  
-  Costos estimados: **+700 millones de dólares** en multas, reparaciones y demandas.  
-  Directivos renunciaron, incluido el CEO.  
-  Considerado uno de los peores fallos de ciberseguridad de la historia.

---

## Pruebas que faltaron

| Tipo de prueba | Habría prevenido | Por qué era crítica |
|----------------|------------------|----------------------|
| Pruebas de vulnerabilidad automatizadas (SAST/DAST) | Detección del CVE-2017-5638 | Herramientas de escaneo lo detectaban al instante. |
| Pruebas de gestión de parches | Verificar que todos los sistemas estuvieran actualizados | Equifax no tenía inventario claro de servidores. |
| Pruebas de penetración | Comprobación de explotación del RCE | El exploit era fácil de replicar. |
| Pruebas de monitoreo y detección | Alertas ante actividad anómala | Los atacantes permanecieron meses sin ser detectados. |

---

#  Caso 2 — OWASP Top 10 (Aplicaciones Web – Global)

## ¿Qué es OWASP?

El **OWASP Top 10** es la clasificación más importante de riesgos de seguridad en aplicaciones web. Resume los fallos más frecuentes y peligrosos que afectan a empresas de todo el mundo.

---

## Tabla de riesgos OWASP Top 10 (versión moderna)

| Código | Riesgo | Descripción breve | Impacto típico |
|--------|--------|-------------------|----------------|
| A01 | Broken Access Control | Fallas en controles de acceso que permiten ver o modificar recursos no autorizados. | Exposición de datos, cuentas comprometidas. |
| A02 | Cryptographic Failures | Cifrado débil o inexistente. | Robo de datos sensibles. |
| A03 | Injection | Comandos maliciosos (SQL, NoSQL, OS). | Acceso total a BD, pérdida de datos. |
| A04 | Insecure Design | Arquitecturas débiles, falta de validaciones. | Vulnerabilidades sistémicas. |
| A05 | Security Misconfiguration | Errores en configuraciones, puertos abiertos, servicios innecesarios. | Explotación de sistemas enteros. |
| A06 | Vulnerable Components | Uso de software con fallos conocidos (Ej: Equifax). | Ejecución remota de código. |
| A07 | Identification & Authentication Failures | Errores en login, tokens, sesiones. | Cuenta secuestrada. |
| A08 | Software & Data Integrity Failures | Actualizaciones no verificadas, CI/CD inseguro. | Supply chain attacks. |
| A09 | Security Logging & Monitoring Failures | Falta de registros y alertas. | Intrusiones no detectadas. |
| A10 | Server-Side Request Forgery (SSRF) | Manipulación de solicitudes del servidor. | Acceso a redes internas. |

---

## ¿Por qué ocurren estos problemas?

- Falta de pruebas de seguridad desde etapas tempranas.  
- Equipos de desarrollo sin capacitación en ciberseguridad.  
- Dependencias vulnerables y no auditadas.  
- Validaciones insuficientes en entrada de datos.  
- Ausencia de pruebas automatizadas en pipelines CI/CD.

---

## Pruebas necesarias para prevenir OWASP Top 10

| Tipo de prueba | Previene | Beneficio |
|----------------|---------|-----------|
| Pruebas DAST | Inyección, XSS, fallos de acceso | Escanea app en ejecución. |
| Pruebas SAST | Vulnerabilidades en código | Encuentra errores antes del deploy. |
| Pruebas IA/ML para análisis de patrones | Ataques complejos y anómalos | Detecta comportamiento irregular. |
| Pentesting ético | Riesgos OWASP reales | Simula ataques del mundo real. |
| Pruebas de configuración | Misconfiguration, SSRF | Asegura entornos seguros. |

---

#  Caso 3 — Inyección SQL (Global, múltiples empresas)

La **inyección SQL** es una de las vulnerabilidades más antiguas y explotadas del mundo. Permite que un atacante ejecute comandos SQL maliciosos manipulando entradas no validadas.

---

## Casos reales emblemáticos

| Año | Empresa / País | Descripción del ataque | Consecuencias |
|-----|----------------|------------------------|----------------|
| 2008 | Heartland Payment Systems (EE. UU.) | SQL Injection permitió instalar malware en servidores de pagos. | Datos de 130 millones de tarjetas comprometidas. |
| 2011 | Sony PlayStation Network (Global) | SQL Injection afectó los servidores de login. | 77 millones de cuentas robadas; caída de 23 días. |
| 2014 | Sistema de votación de Hong Kong | SQL Injection expuso bases de datos internas. | Datos electorales filtrados. |
| 2020 | Varias PYMES en Latinoamérica | SQL Injection en sistemas PHP sin sanitización. | Secuestro de bases de datos y ransomware. |

---

## ¿Cómo funciona una inyección SQL?

Ejemplo simple:


Esto convierte una consulta insegura en:

```sql
SELECT * FROM usuarios WHERE usuario='' OR '1'='1';


## Causas Típicas

- Entradas sin sanitizar.  
- Falta de *prepared statements*.  
- Uso de concatenaciones directas en SQL.  
- Falta de pruebas de seguridad automatizadas.  
- Validación insuficiente en formularios y APIs.  

---

## Pruebas que Habrían Prevenido Estos Ataques

| Tipo de prueba | Prevención | Beneficio |
|----------------|------------|-----------|
| Pruebas de inyección (Fuzzing) | SQLi, NoSQLi, XPath Injection | Detectan entradas manipulables. |
| Pruebas de validación de entrada | Sanitización incorrecta | Refuerzan seguridad del backend. |
| Pruebas SAST | Concatenación de strings inseguros | Identifica patrones peligrosos. |
| Pruebas DAST | SQLi explotable en ejecución | Simula ataques reales. |
| Pentesting | Escala y gravedad del ataque | Permite remediar antes del despliegue. |

---

##  Conclusión General

Los tres casos analizados —**Equifax**, los riesgos del **OWASP Top 10** y las **inyecciones SQL**— demuestran que:

- La falta de pruebas de seguridad puede comprometer **millones de datos personales**.  
- Las vulnerabilidades explotadas suelen ser **errores evitables**.  
- Las empresas que no aplican parches, no validan entradas y no monitorean sistemas quedan expuestas a **pérdidas multimillonarias**.  
- El testing de seguridad debe ser **continuo**, **automatizado** y estar presente desde la etapa de **diseño** (*Shift Left Security*).  
- La prevención no solo es una práctica técnica: es una **responsabilidad ética** en el desarrollo de software seguro y confiable.  

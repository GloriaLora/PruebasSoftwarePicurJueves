# Investigaci¢n del equipo financiero
# Desastres Financieros y Bancarios  
### Casos reales de errores de software en sistemas bancarios que causaron pérdidas millonarias

---

## Caso 1 — Knight Capital Group (Estados Unidos, 2012)

| Año | Empresa | Descripción | Monto de pérdidas |
|-----|----------|--------------|--------------------|
| 2012 | **Knight Capital Group (EE. UU.)** | En agosto de 2012, la firma de trading automatizado Knight Capital implementó un nuevo sistema para manejar órdenes bursátiles en la Bolsa de Nueva York. Un error en la actualización del software hizo que un servidor ejecutara un código antiguo diseñado solo para pruebas, provocando compras y ventas masivas erróneas durante 45 minutos y generando gran volatilidad en el mercado. | **440 millones de dólares** en menos de una hora. |

---

### ¿Qué salió mal y qué pruebas faltaron?

**Contexto:**  
Knight Capital era una de las firmas más grandes de trading automatizado en Estados Unidos. En agosto de 2012, implementó un nuevo sistema para manejar órdenes bursátiles en la Bolsa de Nueva York (NYSE).

**Errores principales:**
- Se activó software de prueba obsoleto (de 2003) en un servidor de producción.  
- Solo 7 de los 8 servidores se actualizaron correctamente; uno seguía corriendo el código antiguo.  
- El sistema ejecutó una rutina llamada **“Power Peg”**, diseñada solo para pruebas internas.  
- El algoritmo comenzó a comprar y vender acciones a gran velocidad (4 millones de órdenes en 45 minutos).  

**Consecuencias:**
- Pérdidas directas: **$440 millones en 45 minutos**.  
- La empresa quedó prácticamente en bancarrota y fue adquirida por Getco.  
- La **SEC** multó a Knight Capital con **$12 millones** por deficiencias en sus controles tecnológicos.

**Pruebas que faltaron:**
- Pruebas de **integración** entre servidores.  
- Pruebas de **regresión**, para detectar código antiguo reactivado.  
- Pruebas de **simulación o sandbox trading** antes de producción.  
- Pruebas de **control de versiones y despliegue continuo (DevOps QA)**.

---

## Caso 2 — TSB Bank (Reino Unido, 2018)

| Año | Empresa | Descripción | Monto de pérdidas |
|-----|----------|--------------|--------------------|
| 2018 | **TSB Bank (Reino Unido)** | En abril de 2018, el TSB Bank realizó una migración de datos para trasladar millones de cuentas de la infraestructura de Lloyds Banking Group a una nueva plataforma propia. La migración falló, millones de clientes no pudieron acceder a sus cuentas, algunos vieron datos de otros usuarios y se generaron errores en transacciones. | **Aproximadamente 400 millones de dólares** en reparaciones y compensaciones. |

---

## Caso 3 — Bank of New York Mellon (Estados Unidos, 1996)

| Año | Empresa | Descripción | Monto de pérdidas |
|-----|----------|--------------|--------------------|
| 1996 | **Bank of New York Mellon (EE. UU.)** | En noviembre de 1996, un error en el software de procesamiento de pagos impidió liquidar operaciones de bonos del Tesoro durante un día completo. El banco no pudo procesar miles de transacciones y tuvo que pedir un préstamo de emergencia a la Reserva Federal para mantener la liquidez operativa. | **Pérdidas directas:** $5 millones + **préstamo de emergencia:** $23 mil millones para sostener operaciones. |

---

## Tipos de pruebas críticas en sistemas financieros

| Tipo de prueba | Propósito | Previene |
|----------------|------------|-----------|
| **Pruebas de regresión** | Garantizan que actualizaciones no afecten funciones existentes. | Reactivación de código obsoleto o fallas tras parches. |
| **Pruebas de integración** | Aseguran que módulos (pagos, riesgo, contabilidad) interactúen correctamente. | Inconsistencias entre sistemas. |
| **Pruebas de estrés y carga** | Simulan transacciones masivas o picos de demanda. | Colapsos en periodos de alto tráfico. |
| **Pruebas de seguridad y cumplimiento** | Validan cifrado, autenticación y cumplimiento (PCI DSS, Basel III). | Fraudes y accesos no autorizados. |
| **Pruebas de failover y continuidad** | Verifican la recuperación ante fallas. | Pérdidas por caídas o apagones. |

---

## Caso especial: El Bug del Año 2000 (Y2K)

**Qué era el problema:**  
Los sistemas antiguos almacenaban años con dos dígitos (“99” para 1999).  
Al llegar el 2000 (“00”), los programas habrían interpretado la fecha como 1900, causando errores en cálculos de intereses, vencimientos y pagos.

**Riesgos potenciales:**
- Cálculos erróneos en saldos e intereses.  
- Fallos en cajeros automáticos y transferencias.  
- Colapsos en sistemas interbancarios.

**Cómo se previno:**
- Proyectos globales de remediación entre 1997 – 1999.  
- Reescritura de millones de líneas de código COBOL.  
- Pruebas de regresión y simulaciones adelantando la fecha a 1 de enero de 2000.  
- Coordinación internacional entre bancos centrales.

**Resultado:**  
El cambio de milenio ocurrió **sin incidentes graves**, gracias a la planificación y las pruebas masivas.

---

### Conclusión general

Los desastres financieros analizados demuestran que **la falta de pruebas adecuadas puede causar pérdidas multimillonarias, afectar mercados globales y destruir la confianza de los clientes**.  
Las **pruebas de regresión, integración, estrés y seguridad** son esenciales para garantizar la estabilidad del software financiero.

---
*Equipo 1 — Desastres Financieros y Bancarios (PICUR Jueves)*  

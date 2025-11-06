# Caso 1

**Explica el caso de Equifax 2017: ¿qué vulnerabilidad explotaron y qué pruebas de seguridad faltaron?**

| **Aspecto**                  | **Descripción** |
|------------------------------|-----------------|
| **Vulnerabilidad explotada** | CVE-2017-5638 en Apache Struts (fallo en parser de Jakarta multipart) que permitió ejecución remota de código (RCE). |
| **Datos comprometidos**      | ~147 millones de personas: SSN, fechas de nacimiento, licencias de conducir y otros datos sensibles. |
| **Causa raíz**               | Falta de gestión adecuada de parches y de inventario de activos vulnerables; el servidor no fue actualizado a tiempo. |
| **Pruebas de seguridad faltantes** | Pentest enfocado en endpoints con subida/parsing de archivos y cabeceras; pruebas de RCE; escaneos de vulnerabilidades sobre componentes de terceros. |
| **Impacto / costo**          | Acuerdos legales por unos USD 575-700 millones, además de daño reputacional y costos de respuesta al incidente. |

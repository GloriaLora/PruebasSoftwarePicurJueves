# Caso 1

**Explica el caso de Equifax 2017: ¿qué vulnerabilidad explotaron y qué pruebas de seguridad faltaron?**

| **Aspecto**                  | **Descripción** |
|------------------------------|-----------------|
| **Vulnerabilidad explotada** | CVE-2017-5638 en Apache Struts (fallo en parser de Jakarta multipart) que permitió ejecución remota de código (RCE). |
| **Datos comprometidos**      | ~147 millones de personas: SSN, fechas de nacimiento, licencias de conducir y otros datos sensibles. |
| **Causa raíz**               | Falta de gestión adecuada de parches y de inventario de activos vulnerables; el servidor no fue actualizado a tiempo. |
| **Pruebas de seguridad faltantes** | Pentest enfocado en endpoints con subida/parsing de archivos y cabeceras; pruebas de RCE; escaneos de vulnerabilidades sobre componentes de terceros. |
| **Impacto / costo**          | Acuerdos legales por unos USD 575-700 millones, además de daño reputacional y costos de respuesta al incidente. |


Referencia caso 1: Equifax. (2018). Statement on the 2017 cybersecurity incident. Equifax Press Release.
https://investor.equifax.com/news

Federal Trade Commission (FTC). (2019, July 22). Equifax to pay $575 million as part of settlement with FTC, CFPB, and states related to 2017 data breach.
https://www.ftc.gov/news-events/news/press-releases/2019/07/equifax-to-pay-575-million-part-settlement

United States House of Representatives, Committee on Oversight and Government Reform. (2018, December). The Equifax data breach.
https://oversight.house.gov/report/the-equifax-data-breach
# Caso 1 – Equifax (2017, Estados Unidos)

| **Elemento** | **Descripción** |
|---------------|-----------------|
| **Tipo de falla** | Vulnerabilidad crítica no parcheada en un componente de terceros (Apache Struts – CVE-2017-5638). |
| **Causa principal** | La compañía Equifax, ubicada en Atlanta (EE. UU.), no aplicó una actualización de seguridad publicada dos meses antes. Su equipo de TI no tenía control sobre qué servidores usaban esa versión vulnerable de Apache Struts, y además un certificado interno de monitoreo estaba vencido, lo que impidió detectar el ataque a tiempo. La vulnerabilidad permitió a los atacantes ejecutar código remoto en los servidores. |
| **Pruebas faltantes** | Faltaron pruebas de penetración (pentesting), escaneos automáticos de vulnerabilidades y verificación de componentes desactualizados. No se aplicaron pruebas de parcheo ni auditorías de seguridad continuas sobre frameworks externos. |
| **Consecuencias** | Se comprometieron los datos personales de 147 millones de personas en Estados Unidos, incluyendo números de seguridad social y licencias de conducir. La empresa pagó más de 700 millones de dólares en multas, demandas colectivas y compensaciones. |
| **Patrón común identificado** | Falta de gestión de vulnerabilidades y pruebas de seguridad periódicas. El incidente demuestra que ignorar un parche o no probar componentes externos puede causar el colapso de una empresa entera. |

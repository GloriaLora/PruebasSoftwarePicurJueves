# Caso 3 – Inyección SQL (Varios países y empresas)

| **Elemento** | **Descripción** |
|---------------|-----------------|
| **Tipo de falla** | Inyección SQL por falta de validación y consultas inseguras en bases de datos. |
| **Causa principal** | Esta falla se ha registrado en distintas partes del mundo, en empresas como TalkTalk (Reino Unido, 2015), Heartland Payment Systems (Estados Unidos, 2008) y Yahoo Voices (EE. UU., 2012). Todas tenían formularios o APIs que no validaban correctamente los datos del usuario. Los atacantes insertaron comandos SQL para extraer información confidencial directamente desde las bases de datos. |
| **Pruebas faltantes** | No se hicieron pruebas de inyección SQL, escaneos DAST, ni revisiones de código enfocadas en la seguridad de consultas. Tampoco se validaron entradas o se aplicaron consultas parametrizadas. Faltaron pruebas automatizadas y manuales para simular ataques de inyección. |
| **Consecuencias** | TalkTalk perdió datos de 156 000 clientes; Heartland expuso millones de tarjetas de crédito; y Yahoo filtró 450 000 credenciales. Todas enfrentaron multas, sanciones y daños irreversibles en su reputación. |
| **Patrón común identificado** | No validar las entradas del usuario ni proteger las consultas SQL lleva a resultados catastróficos. El patrón global es no realizar pruebas básicas de seguridad sobre los puntos de entrada de datos. |

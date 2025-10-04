# **Requisitos\_LiftSafe**

Este documento presenta los requisitos funcionales, no funcionales y restricciones identificados a partir de entrevistas realizadas a distintos actores clave del proyecto **LiftSafe**, una aplicación destinada a la gestión de inspecciones técnicas de ascensores.

## **Análisis de Entrevistas**

### **Análisis de la Entrevista \#1 (Técnico de campo)**

**Funcionalidades Identificadas:**

* "muchas veces estamos en sótanos sin señal, pero igual debemos registrar la inspección" → Registro y consulta offline.

* "sería mejor que la aplicación ya tenga plantillas con los campos específicos del equipo" → Plantillas digitales adaptativas.

* "cuando tomo una foto debería quedar vinculada automáticamente al punto que estoy inspeccionando" → Vinculación automática de evidencias.

* "al terminar, debería salir un borrador del informe para revisarlo con el cliente" → Generación de borradores en campo.

* "el cliente debería poder firmar en el mismo dispositivo" → Firma digital en sitio.

**Restricciones No Funcionales Identificadas:**

* "La aplicación debe funcionar en sótanos o áreas sin señal" → Disponibilidad offline-online sin duplicados.

* "no puede tardar más de unos segundos en guardar la observación" → Tiempo de respuesta ≤ 3 segundos.

* "que sea fácil de usar, porque no todos los técnicos son expertos en sistemas" → Usabilidad e interfaz intuitiva.

### **Análisis de la Entrevista \#2 (Coordinador de operaciones)**

**Funcionalidades Identificadas:**

* "necesito ver qué inspecciones están pendientes, en curso y finalizadas" → Dashboard con estado de inspecciones.

* "que los informes ya no pasen por papel, sino que yo los pueda aprobar digitalmente" → Flujos de trabajo digitales y firma electrónica.

* "sería útil sacar reportes de cumplimiento mensual" → Módulo de análisis y reporting.

**Restricciones No Funcionales Identificadas:**

* "no podemos esperar más de unos segundos cuando se está actualizando un reporte" → Tiempo de respuesta ≤ 3 segundos.

* "tiene que estar disponible todo el tiempo, porque los técnicos trabajan incluso fines de semana" → Disponibilidad 24/7 (99.9%).

* "debe ser tan sencillo que un técnico pueda aprender a usarlo sin capacitación extensa" → Usabilidad alta.

---

### **Análisis de la Entrevista \#3 (Gerente de TI)**

**Aspectos Técnicos Identificados:**

* "esto debe integrarse con nuestros sistemas de contabilidad y CRM" → Integración con sistemas corporativos vía API.

* "los técnicos solo deben ver lo que les corresponde" → Gestión de roles y accesos.

* "si se pierde un dispositivo, la información ya debe estar respaldada en la nube" → Respaldo automático y recuperación de información.

**Restricciones No Funcionales Identificadas:**

* "el sistema debe poder escalar a cientos de inspectores en paralelo" → Escalabilidad.

* "todo dato sensible debe ir encriptado con un estándar fuerte, como AES-256" → Seguridad de datos.

* "la recuperación ante fallas no puede tardar más de 24 horas" → Recuperación ≤ 24 horas.

* "los técnicos usan Android y algunos iOS, así que debe funcionar en ambos" → Compatibilidad multiplataforma.

* "la aplicación debe cumplir con RETIE y la protección de datos (RGPD)" → Cumplimiento normativo.

* "debe ser modular, que si mañana quiero conectar otro sistema sea posible" → Mantenibilidad con APIs estándar.

##  **Requisitos Consolidados**

### **Requisitos Funcionales**

* F-001: Registro y consulta offline.

* F-002: Plantillas digitales adaptativas.

* F-003: Vinculación automática de evidencias.

* F-004: Generación de borradores en campo.

* F-005: Firma digital en sitio.

* F-006: Dashboard de inspecciones.

* F-007: Flujos de trabajo digitales.

* F-008: Módulo de análisis y reporting.

* F-009: Integración con sistemas corporativos.

* F-010: Gestión de roles y accesos.

* F-011: Respaldo automático de información.

### **Requisitos No Funcionales**

* NF-001: Disponibilidad offline-online sin duplicados.

* NF-002: Tiempo de respuesta ≤ 3 segundos.

* NF-003: Usabilidad alta, interfaz intuitiva.

* NF-004: Disponibilidad 24/7 (99.9%).

* NF-005: Escalabilidad a cientos de inspectores concurrentes.

* NF-006: Seguridad con encriptación AES-256.

* NF-007: Recuperación ante fallas en ≤ 24 horas.

* NF-008: Compatibilidad Android e iOS.

* NF-009: Cumplimiento con RETIE y RGPD.

* NF-010: Arquitectura modular y mantenible.

### **Restricciones**

* R-001: Funcionamiento en zonas sin conectividad.

* R-002: Cumplimiento estricto de RETIE y RGPD.

* R-003: Respaldo diario en la nube.

* R-004: Disponibilidad mínima de 99.9%.

---

## **4\. Conclusiones**

El análisis de entrevistas permitió identificar un conjunto claro de **requisitos funcionales y no funcionales** para el proyecto LiftSafe. Se confirma que la prioridad es garantizar la **operatividad offline, la usabilidad para técnicos de campo, y la integración segura con los sistemas corporativos**.

El sistema deberá cumplir estándares normativos, ser escalable y contar con **altos niveles de seguridad y disponibilidad** para asegurar la continuidad de las operaciones.

##  **Anexo – Transcripciones de Entrevistas**

### **Entrevista 1: Técnico / Inspector de Campo**

**Pregunta:** ¿Podría presentarse y contarnos cómo es un día típico de inspección?  
 **Respuesta:** Soy técnico de mantenimiento e inspector de campo. Reviso la seguridad, hago la inspección visual y luego la técnica: cables, frenos, puertas, cabina y sistema eléctrico. Anoto en libreta y tomo fotos con mi celular. Con una aplicación en tableta podría registrar todo en el momento y ahorrar tiempo.

**Pregunta:** ¿Qué herramientas utilizan actualmente para registrar la información?  
 **Respuesta:** Uso papel y bolígrafo. Las fotos las tomo con el celular, pero luego debo pasarlas al computador. Una aplicación me permitiría registrar todo en un solo dispositivo.

**Pregunta:** ¿Qué tipo de datos registra normalmente?  
 **Respuesta:** Medidas de holgura, estado de frenos, cables, iluminación, pruebas de seguridad… unas 25 a 30 observaciones. Todo lo hago manual, pero con una aplicación móvil podría organizar esos datos en plantillas.

**Pregunta:** ¿Cómo manejas las fotos y vídeos?  
 **Respuesta:** Hoy las paso manualmente al ordenador. Es muy demorado. Si la app las vinculara de inmediato al informe, sería ideal.

**Pregunta:** ¿Necesita consultar información histórica de los equipos?  
 **Respuesta:** Sí. Actualmente debo llamar a una oficina o buscar carpetas impresas. Con una tableta podría abrir una vez el historial del ascensor.

**Pregunta:** ¿Qué problemas tiene con la conectividad en campo?  
 **Respuesta:** Muchos. En sótanos no hay señal. La aplicación debería funcionar sin internet y sincronizar después.

**Pregunta:** ¿Cómo transforma sus notas en el informe final?  
 **Respuesta:** En la oficina paso todo un Word o Excel. Eso puede tardar hasta 3 horas. Con una aplicación, el informe quedaría prácticamente listo en el sitio.

**Pregunta:** ¿Qué partes del informe son críticas?  
 **Respuesta:** Datos técnicos, observaciones, fotos y firmas. Si pudiera firmar directamente en la tableta con el cliente, sería perfecto.

**Pregunta:** En conclusión, ¿qué espera de un sistema ideal?  
 **Respuesta:** Una aplicación móvil o para tableta que funciona sin conexión, con plantillas inteligentes, fotos automáticas y firmas digitales.

### **Entrevista 2: Jefe de Mantenimiento / Coordinador de Operaciones**

**Pregunta:** ¿Podría presentarse y contarnos cómo gestionan actualmente las inspecciones?  
 **Respuesta:** Soy coordinador de operaciones y asigno y reviso inspecciones. Hoy usamos correo o WhatsApp, lo cual es muy informal. Con una aplicación podría asignar tareas y ver el avance en tiempo real.

**Pregunta:** ¿Cómo monitorea el progreso de las inspecciones?  
 **Respuesta:** Solo me entero cuando llega el informe final. Con un tablero en la aplicación, vería en qué etapa está cada técnica.

**Pregunta:** ¿Cómo recibe y prueba los informes?  
 **Respuesta:** Los recibos en PDF o Word y los reviso manualmente. Sería más ágil aprobarlos digitalmente en la aplicación.

**Pregunta:** ¿Qué problemas se encuentran con el proceso actual?  
 **Respuesta:** Se pierde tiempo transcribiendo datos, los informes no son uniformes y se cometen errores. Con plantillas predefinidas todo sería más consistente.

**Pregunta:** ¿Ha tenido incidentes por retrasos?  
 **Respuesta:** Sí. Algunos informes llegaron tarde y generaron quejas de clientes. Una aplicación aceleraría la entrega.

**Pregunta:** ¿Qué informes necesitaría el nuevo sistema?  
 **Respuesta:** Indicadores de cumplimiento, productividad, tiempos y alertas de retrasos.

**Pregunta:** ¿Cuál sería su prioridad principal con este sistema?  
 **Respuesta:** Mejorar la eficiencia del equipo y aumentar la satisfacción del cliente.

---

### **Entrevista 3: Gerente de TI**

**Pregunta:** ¿Podría presentarse y describir la infraestructura tecnológica actual de la empresa?  
 **Respuesta:** Soy gerente de TI. Tenemos servidores en la nube, correo corporativo y un sistema contable. No utilizamos ERP completo. Una aplicación conectada al móvil lo integraría todo.

**Pregunta:** ¿Qué requisitos técnicos debería cumplir el nuevo sistema?  
 **Respuesta:** Debe ser rápido, seguro, fácil de usar, trabajar offline y sincronizar después. Además, integrese con contabilidad y CRM.

**Pregunta:** ¿Qué nivel de seguridad es crítico?  
 **Respuesta:** Autenticación segura, encriptación de datos y control de accesos por roles. La aplicación debe proteger toda la información de clientes e inspecciones.

**Pregunta:** ¿Qué estrategia de respaldo se requiere?  
 **Respuesta:** Respaldos automáticos en la nube todos los días y recuperación en máximo 24 horas.

**Pregunta:** ¿Qué tan escalable debe ser el sistema?  
 **Respuesta:** Muy escalable. Debe soportar más inspectores y más clientes sin problemas.

**Pregunta:** ¿Qué recomienda para que sea adoptado por el personal?  
 **Respuesta:** Que sea simple y práctico. Si la aplicación es complicada, los técnicos no la usarán.


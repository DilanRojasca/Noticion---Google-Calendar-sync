# Notion - Google Calendar Sync

## 📌 Descripción
Este proyecto implementa la **integración entre Notion y Google Calendar**, permitiendo visualizar y sincronizar reuniones de **Google Meet** directamente desde una base de datos en Notion.  

El sistema se desarrolla siguiendo el **SDLC (Software Development Life Cycle)**, aplicando buenas prácticas de **seguridad, pruebas y despliegue automatizado**.

---

## 🎯 Objetivo
Desde una página en Notion, poder:
- Ver reuniones programadas en **Google Calendar**.  
- Sincronizar eventos automáticamente en una base de datos de **Notion**.  
- Mostrar las próximas reuniones (24h o semana actual).  

---

## ⚠️ Riesgos Identificados
- Cambios en las **APIs de Google o Notion**.  
- Límites de **cuotas de uso de las APIs**.  
- Exposición de **credenciales en texto plano**.  

---

## 📋 Análisis de Requisitos

### ✅ Requisitos Funcionales
1. Recuperar reuniones programadas en Google Calendar que tengan enlace de Google Meet.  
2. Insertar o actualizar automáticamente los eventos en una base de datos de Notion.  
3. Mostrar en Notion las reuniones próximas (24h o semana actual).  
4. Sincronizar cambios (modificación o eliminación) entre Google Calendar y Notion.  

### ⚙️ Requisitos No Funcionales
1. Manejo de al menos **10.000 eventos diarios**.  
2. Disponibilidad **≥ 99%**.  
3. Compatibilidad con **múltiples workspaces** de Notion y **varios calendarios** de Google.  

### 🔐 Requisitos de Seguridad
- Almacenar tokens en un **gestor seguro** (no en texto plano).  
- Registrar logs de sincronización y accesos a tokens, **sin exponer credenciales**.  

---

## 🏗️ Diseño

### 📡 Arquitectura
- **Notion**: arquitectura SaaS basada en la nube, con backend en **microservicios**.  
- Se plantea un **middleware** como intermediario entre Google Calendar API y Notion API.  
- Comunicaciones cifradas con **HTTPS/TLS**.  

### 🛡️ Modelado de Amenazas (Threat Modeling)
- **Exposición accidental de enlaces de Meet** → mitigado con **control de permisos en Notion**.  

### 🛠️ Controles y Contramedidas
- Logging seguro y auditoría de eventos.  
- Uso de **OAuth 2.0** para autenticación y gestión de sesiones.  
- Tokens cifrados en tránsito y en reposo.  

---

## 💻 Desarrollo

### 🔑 Prácticas de Codificación Segura
- Autenticación mediante **OAuth 2.0** (Google & Notion).  
- Tokens gestionados con **expiración y renovación**.  
- **HTTPS/TLS** para comunicaciones.  
- Variables de entorno seguras o gestores de secretos.  

### 🤖 Herramientas de Análisis
- **SAST (Análisis Estático):** SonarQube → identifica vulnerabilidades en código.  
- **DAST (Análisis Dinámico):** OWASP ZAP → detecta configuraciones inseguras y fallos en la gestión de tokens.  

---

## 🧪 Pruebas
- **Pruebas funcionales**: validación de sincronización entre Notion y Google Calendar.  
- **Pruebas de seguridad**: penetration testing + análisis con SAST y DAST.  
- **Pruebas adicionales** en caso de integración con IA → detección de riesgos específicos.  

---

## 🚀 Implementación y Despliegue
- **CI/CD** con GitHub Actions o GitLab CI/CD.  
- **Pipelines seguros** para despliegue automatizado.  
- **Firmas digitales** para validar integridad del código.  
- **Monitoreo post-despliegue** para detección temprana de incidentes.  

---

## 🔄 Mantenimiento
- Gestión continua de vulnerabilidades con parches de seguridad oportunos.  
- Actualizaciones regulares y monitoreo constante en producción.  
- Garantía de **estabilidad y seguridad a largo plazo**.  

---

## 📂 Repositorio
🔗 [GitHub - Notion Google Calendar Sync](https://github.com/kitsuyaazuma/notion-google-calendar-sync)

---

## 📚 Bibliografía
- [Notion](https://www.notion.com/es)  
- [Functional vs Non-Functional Requirements](https://visuresolutions.com/es/alm-guide/functional-vs-non-functional-requirements/)  
- [OWASP ZAP](https://www.zaproxy.org/)  

---

## 👨‍💻 Autores
- **Dilan Rojas Carmona**  
- **Sebastián Vélez Guarín**  

**Curso:** Cloud Computing  
**Docente:** Durley López  
**Universidad Católica Luis Amigó**  
📅 **03/10/2025**

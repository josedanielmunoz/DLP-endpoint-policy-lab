# DLP-Security-Policy-Project

# Implementación de Políticas de Seguridad DLP a dispositivos de almacenamiento externo

## Descripción del Proyecto
Este proyecto consiste en el diseño y ejecución de una estrategia de **Prevención de Pérdida de Datos (DLP)** en un entorno corporativo simulado (Windows 10 Pro sobre VirtualBox). El objetivo principal es restringir el uso de medios extraíbles para mitigar riesgos de exfiltración de información y entrada de malware, aplicando el **Principio del Menor Privilegio**.

---

## Parte 1: Estrategia de Políticas DLP

### 1. Introducción
El DLP es una estrategia integral que combina procesos y tecnología para proteger la información sensible en sus tres estados: en uso, en tránsito y en reposo. Su implementación es crítica para el cumplimiento normativo (GDPR, PCI-DSS) y la protección de la propiedad intelectual.

### 2. Clasificación de Datos
Se han establecido tres niveles de sensibilidad:
* **Públicos:** Información de libre divulgación (ej. Marketing).
* **Internos:** Documentación operativa de uso exclusivo del personal.
* **Sensibles:** Información crítica (PII, estados financieros) que requiere bloqueo total de hardware y cifrado.

### 3. Acceso y Control
Se aplica el **Principio del Menor Privilegio (PoLP)**. Por defecto, el acceso a USB está denegado para roles operativos, permitiendo excepciones únicamente a roles técnicos (Administradores) bajo un flujo de revisión documentado.

### 4. Monitoreo, Auditoría y Prevención
* **Monitoreo:** Uso de Microsoft Sysmon y Auditoría nativa de Windows (Event IDs 4656/4663).
* **Prevención:** Implementación de cifrado BitLocker y herramientas de inspección de contenido.
* **Concientización:** Programa de capacitación continua y simulacros de "USB Drop".

---

## Parte 2: Implementación Técnica con Evidencias 

### 1. Configuración del Entorno
* **Hipervisor:** VirtualBox con Extension Pack habilitado.
* **Hardware:** Filtrado de puerto USB 3.0 (xHCI) hacia la VM de Windows 10.

### 2. Aplicación de Directivas de Grupo (GPO)
Se configuró el bloqueo global mediante `gpedit.msc` en la ruta:
`Configuración del equipo > Plantillas administrativas > Sistema > Acceso de almacenamiento extraíble`
* **Denegar acceso a Lectura:** Habilitada.
* **Denegar acceso a Escritura:** Habilitada.

### 3. Gestión de Excepciones
Para permitir acceso solo a administradores, se utilizó la **Consola de Administración de Microsoft (MMC)**, cargando el complemento de directiva enfocado exclusivamente en el grupo **"No administradores"**.

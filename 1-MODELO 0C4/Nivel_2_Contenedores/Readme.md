# Nivel 2: Diagrama de Contenedores (C4 Model)

## Descripción General
El Diagrama de Contenedores detalla la arquitectura de alto nivel elegida para el despliegue del sistema (alineado con la decisión de diseño estipulada en el **ADR-001**). Muestra cómo se distribuye la responsabilidad de la ejecución de la lógica y la persistencia de datos.

## Arquitectura Tecnológica y Contenedores

### 1. Aplicación Web (Monolito Modular)
* **Tecnología:** Java / Spring Boot.
* **Responsabilidad:** Encapsula en un único artefacto ejecutable toda la lógica de negocio del sistema de pasantías. Sirve de manera unificada las vistas de usuario (Frontend) y procesa los flujos de control de todos los casos de uso (`CU-08` al `CU-28`).
* **Protocolo de Comunicación:** Los usuarios acceden de forma segura mediante navegadores web estándar utilizando **HTTPS**.

### 2. Base de Datos Central
* **Tecnología:** Motor de Base de Datos Relacional (PostgreSQL / MySQL).
* **Responsabilidad:** Almacena de forma centralizada todo el modelo de datos del sistema (entidades de empresas, estudiantes, convenios vigentes, vacantes, postulaciones e historiales de auditoría).
* **Estrategia de Conexión:** Para optimizar los recursos del servidor y garantizar un único punto de acceso concurrente, el Monolito se conecta al contenedor de persistencia implementando el patrón de diseño **Singleton** (`ConexionBD`).

---
_Nota: El diagrama visual de este nivel se encuentra definido en el archivo `contenedores.puml` adjunto en esta misma carpeta._
![diagrama de Contexto](http://www.plantuml.com/plantuml/png/XLAnRXD14Etz5Okh82M-Xeeg8R402IGh3hJHU6_YZBItSypkceI_eQH8WUXe_MFCtFbEXp3GtStilFVclJbF6IIN9ioUKVIXrEZkSsxJoweI-BpOKhulcv9GFCUCCIyyDrKR8DhCMSfre4rr-U9iPQKFxzzL3QICegNRIvjuo8lMq6UPSa1tHR0LQC0fpw7FxiojIOVwwcjCcVO_edsl82dg_WdIRBP2IHnFj5jgqYgUklbo_9dhtwkIFBWTU2kaKzUojWEuHoUuemGEWzDngDcmKt6jiCV4Y_dp4Rrf1HCes3NQboviOFP-sRVcNM-hUWKCWsKBaRw0DytAMJQ19YgK77SGzZzXa6FL2MDDWZwpAEpLuTDLxg9kA7OSDOjHTgvm1ASnx30IwtwGQ1jDH8kY-x7qT0rbj6T9fNk2ATdmjATZZxRRUYpskq7GTPmMA4FgdC9jeORqCK_M2ThSKDv_zIpTk-0Wb2PsTixMZnReIUfpxNDKBKhmtwXDXUeTriZ20SHbhja2zEH3bryx3gYeqHL7KJ5pyMPMm3GHSxjyo8EW2m-r6kLv8iXg-szMx1G8xr23XyoT2GrasJ_v_fxK0gh13ze5FnMpgtyPE1sSwDclCVnsjKSy-Vlbfh91T_bHSHHcEC-Z6EDHyXrAXZJro92WbO8Rg0JzFMZ0obLJjruFFbxYKVIBVdgYKGQ-qNlBWL2qX0yjrdOmE81FB-zVueUBEdPv7WBTaLVueCsaPk3-EmyM_ubw9EktJSkImL6yOsaE2S8GF5ZmRsvkLklgUhc-KUHpZ7LfVW40)

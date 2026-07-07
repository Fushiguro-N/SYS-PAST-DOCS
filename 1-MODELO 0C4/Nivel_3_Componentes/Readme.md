# Nivel 3: Diagrama de Componentes (C4 Model)

## Descripción General
Este diagrama desglosa el interior del contenedor de la **Aplicación Web (Monolito)**. Permite evidenciar cómo está estructurado modularmente el backend de la aplicación, dividiendo el sistema en componentes lógicos fuertemente cohesivos que aíslan las responsabilidades de cada conjunto de Casos de Uso.

## Componentes / Módulos Internos

* **Módulo de Empresas:** Centraliza la lógica para dar de alta, modificar y aplicar la baja lógica o inhabilitación de las organizaciones en el sistema (`CU-08`, `CU-09`, `CU-10`).
* **Módulo de Estudiantes:** Controla la gestión de expedientes de los alumnos, la edición de perfiles (como la carga de CV) y la consulta de estados académicos (`CU-11`, `CU-12`, `CU-13`).
* **Módulo de Convenios:** Controla el ciclo documental y de vigencia de las alianzas estratégicas institucionales con las empresas, incluyendo adendas y renovaciones (`CU-14`, `CU-15`).
* **Módulo de Vacantes y Postulaciones:** Gestiona el Core transaccional del negocio: creación de ofertas por las empresas, aprobación y publicación por parte del Director, postulación del alumno y los flujos de aceptación o rechazo (`CU-16` al `CU-21`).
* **Módulo de Seguimiento y Evaluación:** Administra el monitoreo del alumno en la empresa mediante la asignación de docentes, registro de bitácoras periódicas, cálculo automatizado de promedios de desempeño, emisión de constancias con código de verificación QR y cierre de procesos (`CU-24` al `CU-28`).

## Integración de Datos
Todos los componentes lógicos se comunican directamente con el contenedor de la Base de Datos Relacional de manera interna utilizando JDBC/JPA, aprovechando la transaccionalidad nativa para asegurar que las reglas de negocio (como no eliminar empresas con convenios activos) se cumplan de forma estricta.

---
_Nota: El diagrama visual de este nivel se encuentra definido en el archivo `Compoentes.puml` adjunto en esta misma carpeta.
![diagrama de Contexto](http://www.plantuml.com/plantuml/png/VPHBRnCn4CVl-obCJgdKD6qfg70gUOY7Y5IbJQ_Ln3j9ftZjnVO6KiI7uSY1KszSyyKOhtVB9jeqYkJrU1w_-VjnuJnONsGgUK5QgY95SUTzxjxs-nQ-7It9tnNpmg6LHdlK_aYQh9yhq26cvtogQDuVdlKkWsas-TpFm7cqRBeTcYmtEiJa8N_YoIiK8uAbXGm4LthoG2TwOcAqKUHDMBa4n_asVy0boP0h0scqtOKj8T93qVd87tO13y5vvWgmP3fi_d3D2DTtwmmLmg8_HP0-s6-8-tJih8JZJ-JwNmiK5BAmo-OlQC4T2bwVW_p2DOuw1qbojGw-jmDJw1JikbkjtMOcBHGwJZpPFFAdSQ84qYRM64I_pe7uaGZ-FJNQvSXnbbjqq8WEJTJMG7kLMzBB_r71zXwT9wCX85fSSXFM70fcBq3H0qZQF6eHEc8JhQevvyKghs0tI7di3cUzu_D34OOtvN1oVC3Tje0wNwG4tDWEQsDX7-wxD2CT8444TV1xZYbXY0YGx6XznGWIqitlZ2I8Re0vYKodSNZPZiPdOeMQp0vORTwBnGwicmB1_nKjKKi2iHOMjMbe9kiq8WChZOjWPv7eLJlH3SWMfMehrxWqh9hY8aRlbsq26k_BFLweuhvCOHPeFRXgBnNohkVDL9mQSclcrJIolXQW0ktfIJlj5IuBoeXdPXkuiS29nojGHTHbxqOxMceGhiZHhiWP6oIOaz_yaiP6R3QJXn9KLfr8GcjHT0FYMSrwNhB-RDpuqRoRphd801o6i15uuyIGIrjGeVeKemnnDdPygJCGaW71UafDI9YmK-FfsBw1OxtYLqRaw2dgrxmp7BmRsxmK-y9PiqoRjkZckMrU4HdDxJ7r6Me-0lMXM6-VXRRmxQsUngS3ThP86yvMQxMbKAd_S3eR1O4_ZGR3giQM5C_xrKq_xnNRV3vLivbslmjkkyZ-0G00)

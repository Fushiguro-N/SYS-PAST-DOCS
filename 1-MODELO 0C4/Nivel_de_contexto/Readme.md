# Nivel 1: Diagrama de Contexto del Sistema (C4 Model)

## Descripción General
El Diagrama de Contexto establece el límite del **Sistema de Gestión de Pasantías**, permitiendo visualizar a alto nivel cómo interactúan los usuarios clave del negocio y los sistemas externos con la plataforma sin entrar en detalles tecnológicos.

## Actores y Roles del Sistema
* **Estudiante:** Actor principal que interactúa buscando vacantes publicadas, postulando mediante el envío de su CV (`CU-19`) y visualizando el estado de su proceso.
* **Representante de Empresa:** Organización aliada encargada de registrar su información corporativa (`CU-08`), publicar ofertas de pasantías (`CU-16`) y evaluar o descartar a los alumnos postulantes (`CU-20`, `CU-21`).
* **Director / Administrador:** Usuario con permisos de gestión total que administra empresas, registra y renueva convenios institucionales (`CU-14`, `CU-15`), aprueba vacantes, asigna supervisores y realiza el cierre definitivo de los expedientes (`CU-28`).
* **Docente Supervisor:** Encargado del acompañamiento académico del pasante, responsable de asentar las bitácoras y visitas de seguimiento periódico (`CU-25`).

## Interacciones con Sistemas Externos
* **Sistema Académico:** Es un sistema externo esencial para el flujo del negocio. El Sistema de Pasantías consume su API para importar y validar de forma automática que los estudiantes cuenten con matrícula vigente y cumplan estrictamente con los requisitos académicos necesarios antes de permitirles postular (`CU-11`).

---
_Nota: El diagrama visual de este nivel se encuentra definido en el archivo `contexto.puml` adjunto en esta misma carpeta._
![diagrama de Contexto](http://www.plantuml.com/plantuml/png/RLBDRXDD4BplKyoNaoDzjX4973Z5Fn4GES6mYJX6lRFDPgIPwTNyR68G3yEHGqwvSTqNezi_na5ObZpJxkhggfgpc22ax6pnd_7QvXhLNKfjV3CU1xWVDIRTvIf739fyGfz6cjoujU05CuofjgOQpqw7IodTN2x63cB2mANR6IF0U0oZLkONoIIBQcwW2U10CPDqeCUQ0aOrLALXwEQVjnYJwP-yd9SGUNR_2B4ebXWY-K6E6OAX-BywkjaUkTFk9Xnn_JocN1i68dUTkvOfW4zp4r0d2b8jSukXCr5kHyT5KQu4VJkbx6i8gu4ZJzOauccB_j6PX8SaprPZlFfMAFxiLG_kiPgqBOCdhJKQz5hFPwpKu78x-5WMlO0Er5YLRJ2-KLEY9DNIX0wLXQWwfeCeR5lLQgNQG1eZg4GrAClV_gbX2cdos93c9aTrjjp-5MeOiRfdkyshGLqnonGY2cWEYQAQeKy1hD0lAQOcOFbnmQjThlXNgXFhGADVKnh_XG9VTodXtcAmsNd9fWEzzL-Jxz1BIYjLcTJ_q1GscY8ssJZ3p3HQkp6VpjIWP2ii9lB7lFdtVJBd3saGD-vFDDJeZ9PmTe58hVyfnRM4G1soEf4cJFZdGOWVnIUq1-ze7zPD18LMjHGIMELm0v61xwwlboNRSGKTDb1Ja31vaWpQmTUkBX1P9qOTJBLR84VmDQdiGSp0XxLj_IylgHtAPVZ6z6N6a4YTdBnuFNnrUlBoBw9_sC3fnkmE56-3EDpzelnmfIRBzppj37sTtMy0
)

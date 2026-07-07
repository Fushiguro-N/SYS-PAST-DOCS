CASOS DE USO DEL SISTEMA DE PASANTIAS EN LA ESCUELA DE ADMINSTRACION

CU01: Registrar reporte contable

1. El Proceso Principal (Caso de Uso Base)
   CU01: Registrar reporte contable: Es la funcionalidad central. El actor "Estudiante Contable" interactúa directamente con ella ("Accede") para subir y registrar su informe al sistema.

2. Las Relaciones Obligatorias (<<include>>)
   El caso de uso principal depende obligatoriamente de dos subprocesos para completarse con éxito. Cada vez que se registra un reporte, el sistema hace lo siguiente de forma automática:
   Validar formato y tamaño de archivo: El sistema comprueba inmediatamente si el archivo cumple con las reglas permitidas.
   Almacenar en expediente digital: Si todo está correcto, el sistema guarda el documento de forma permanente en el historial digital del estudiante.

3. El Flujo Excepcional o Alternativo (<<extend>>)
   Mostrar error de archivo inválido: Este caso de uso es opcional y condicional. No ocurre siempre; solo se activa e "inyecta" su comportamiento en el caso de uso principal si la validación previa falla (por ejemplo, si el estudiante sube un formato no permitido o un archivo que pesa demasiado).

En resumen:
El caso de uso permite al Estudiante Contable registrar su reporte, obligando al sistema a validarlo y almacenarlo, abriendo la posibilidad de mostrar un mensaje de error únicamente si el archivo adjunto no es válido.

RP3TIiGm48Nl2ts7eVUxwAsKicNnmWj5h0f2GSPah67pKoR9ieluC3w2px0lPjhzPJKtWUGxPywPcG_88HgTPtwXR8-C1deK2-oe2MjDm2G2savJdkKPYk0OYciVebHe0y7SsO1lcWf03-J3G1qaK3Gl3TpNJNttU5Ct1Npc6QGJFGdqwViPjPB8yExOO72jNKD0WviV1v80MNoefHkjetXTRk4pYreR56IJ2TdMqgedgMX89bMd0kgzkel8VzNpfulBrZvGftpWvC7KEqvYSLehgGqgUoQzTLi9CJjkxJ4lABlSVAUiX-GZacTVmtBIZc0ogVQcS0Mr42J7zUxVfh6VLYUL4rIMoWeT9LNLFzokt3_SEFe8xaQM9Qq2MJb0itH7ymi0

CU02: Logearse

1. El Proceso Principal (Caso de Uso Base)
   CU02: Logearse: Es la funcionalidad central. Los actores "Administrador", "Director" y "Estudiante Contable" interactúan directamente con ella ("Accede") para introducir sus datos e intentar ingresar al sistema SYS PASANTIAS.

2. Las Relaciones Obligatorias (<<include>>)
   El caso de uso principal depende obligatoriamente de dos subprocesos para completarse con éxito. Cada vez que alguien intenta logearse, el sistema hace lo siguiente de forma automática:

Validar credenciales: El sistema comprueba inmediatamente si el usuario y la contraseña ingresados son correctos y existen en la base de datos.

Generar Token JWT: Si la validación es exitosa, el sistema crea automáticamente un token de seguridad (JSON Web Token) para mantener la sesión activa y proteger las futuras consultas del usuario.

3. El Flujo Excepcional o Alternativo (<<extend>>)
   Mostrar Mensaje de error: Este caso de uso es opcional y condicional. No ocurre siempre; solo se activa e "inyecta" su comportamiento en el caso de uso principal si la validación previa falla (por ejemplo, si el usuario se equivoca en su contraseña o el usuario no existe).

En resumen:
El caso de uso permite al Administrador, Director y Estudiante Contable iniciar sesión, obligando al sistema a validar sus credenciales y generar un token JWT, abriendo la posibilidad de mostrar un mensaje de error únicamente si los datos introducidos no son válidos.
bLBDRjD04BvRyZkCt0Ed1b9L227BgaaR1A88oG6424AJtI5iOyz6ksjIKV4ABGTENCexSE7Ec_02y0ZiEjcIbaW5N-oT-Nvcl_6UTMXSszHfSWC6cj-eQMjGgEzV6II1qBKsP86iKxK6gGMnepInCyLpDDX0QqcW9JX94_3FFHIpgT4joq6WmbP_MFQ7_LLJ6qbcGsEesItBYxSgwCTYfTuJz7VJvCEw9mhdeIV_BBgrSx2xV_lEvWbNZfSCIcFquehad-xSA-2K_cU0MFOkQR8SFojberXPPr1gam5Qm52vwEyhG-6hQqbbBXe7rhLIeLz4s9Z3IKqTnYyfo0SMyhGcoAeN5Jmfg_Bnw45PPN7WkBBir_cdZsD-XhMIQCOi34bYeR0csmcsulMxPVClukdvpszdOxvFJ2PmHtf630-VZoBnQE6kaF99CNXwQoU_EId6_4XF2Osb26ymtFmI_iVdBvt7eGuPUOz3Oej75FvByWioaTiTOhOXGjX-kKhyrNOHrU4kb4Bu6wQ93_CwYC_oEaYQn5gldVUAjRGyACyLYxgLL1GRS3wS3PZk7j2JUi6zTSCyfsD7B0Dipx_RvZS0

CU03: Gestionar usuarios

1. El Proceso Principal (Caso de Uso Base) CU03: Gestionar usuarios: Es la funcionalidad central dentro del sistema "SYS PASANTIAS". Los actores "Administrador" y "Director" interactúan directamente con ella ("Accede") para administrar las cuentas y la información de los usuarios en el sistema.

2. Las Relaciones Obligatorias («include»): El caso de uso principal depende obligatoriamente de dos subprocesos para completarse con éxito. Cada vez que se gestionan usuarios, el sistema hace lo siguiente de forma automática:

Validar registros duplicados: El sistema comprueba inmediatamente si los datos del usuario que se intenta registrar o modificar ya existen para evitar duplicidad.

Actualizar niveles de acceso (Roles): El sistema asigna o modifica de manera obligatoria los permisos y roles correspondientes al usuario dentro de la plataforma.

3. El Flujo Excepcional o Alternativo («extend») Mostrar error de duplicado: Este caso de uso es opcional y condicional. No ocurre siempre; solo se activa e "inyecta" su comportamiento en el caso de uso principal si la validación previa de duplicados detecta que los datos ya existen en el sistema (por ejemplo, si se intenta registrar un correo o DNI que ya está en uso).

En resumen: El caso de uso permite tanto al Administrador como al Director gestionar los usuarios, obligando al sistema a validar que no haya registros duplicados y a actualizar sus niveles de acceso, abriendo la posibilidad de mostrar un mensaje de error únicamente si se detecta un dato duplicado durante el proceso.
bL91RjH04BnRyXzQpW4uP64XGWXPLio6HHn020CImWXDPXepYjspwfd9eaJy00v8N16Fu0dyX1Vm16QyEyach0JuOhkwkgfSutth13i_z7bs1MQ6tkhEiv3wntS2XI1DRnWje7MwDw2CH7AOP_P8qqAm6C1RbC8YdEOPXEkUa4ST6qzg5bTXPpglf_FfUcXO8MyPp0sv5RnyfwD-0XjzWZ3ToxCFcvv2ka0z_MVHdPltzmvktzcUSErumQ1cDijBakVJHL0G7VvFW0G7bpnRnIzgDMZIrh5GXWiG5aH4pkO7cZ4-ZIEbEQv6H53N8nJDomQUr4tz-Dd3kYbIc7GSnQzlNpwrz4BqMWa6nYuw6TkIyejUo-1fHs4ltnolI7yAV6wfbiw7yKdG87sCFKO532SWqHgu-jG4v5eIulXsIQOyh6RFRzmghnzMBJs8_v6X8EQj5wpFCmmYVlc5pPzVFxRqoCI2632S28_MP_dJwZXArSO6OVVLkl3NkrKIXxjGXz0g77Neyc-KF4lOn2ycrKPBWLIMccJl5LRL5jvOmXRM61CcoYnficbPblZU8Qb8smztF_m6

CU04: Gestionar solicitudes especificaciones

1. El Proceso Principal (Caso de Uso Base) CU01: Gestionar solicitudes de pasantías: Es la funcionalidad central dentro del sistema "SYS PASANTIAS". El actor "Estudiante" interactúa directamente con ella ("Accede") para iniciar el trámite, y el proceso interactúa a su vez con la "Base de Datos de Pasantías" (actor del sistema) para consultar o almacenar la información.

2. Las Relaciones Obligatorias («include»): El caso de uso principal depende obligatoriamente de dos subprocesos para completarse con éxito. Cada vez que se gestiona una solicitud, el sistema hace lo siguiente de forma automática:

Validar datos obligatorios: El sistema comprueba de inmediato que todos los campos requeridos en el formulario de solicitud estén correctamente completados por el estudiante.

Registrar solicitud (Pendiente): El sistema guarda de forma obligatoria el estado inicial de la postulación como "Pendiente" para su posterior revisión.

3. El Flujo Excepcional o Alternativo («extend») Mostrar error de validación: Este caso de uso es opcional y condicional. No ocurre siempre; solo se activa e "inyecta" su comportamiento en el subproceso de validación si el estudiante olvida completar algún campo obligatorio o ingresa información con un formato incorrecto.

En resumen: El caso de uso permite al Estudiante gestionar sus solicitudes de pasantías, obligando al sistema a validar los datos obligatorios y a registrar la solicitud en estado pendiente en la Base de Datos de Pasantías, abriendo la posibilidad de mostrar un mensaje de error únicamente si la validación de los datos falla durante el proceso.
RLF1Qjj04BqBz0-3JwqXfhaQOU8q9XJIOggsKEXbiZjsXwnspUuuRIZze1vwwYVunpgxKeLgeeFOrRmtRzxCw2e9HZbshgxI0_i3Hkm0ZOJOofCZm6-KGaTrvMWd804YxxyAM8vaX8ElgxegS5XkaXmjenTQ0YPezKPUnl0r9W9BS8CIKZviCIduz1jJmTzSGzEqd8GwNArotYo1VgzLpDhFBMpNxVhTXpVhTWO_wWhqEIOoEUlizSTNbr_yBQLS4aP8mR7XN41HEenAiwoKqMS9Fg5ZgqHRYWltZlTwYXnwHXyMEcEz3KcYiYX6TQX2ZmLd-FJ7JtbQr2P3pkZlQSzzWh5UUB4bRrdxHYzBXXv30xL_3vs5YujLyG9BM1j3TYYlVCenxUZ_aKbyiHfDAQXfs1kdMNFZfvX_yizXHdwpE3TQuFHTr4j6_ypJz46X_VQ4tJY3-NohOmxgsIYPqd8-BvzXuu36XTBUtbE-Qw_Yq3KRu0dmg1h2Hc-BaNUWk6EdMupszAjZ4wPqtKP-xC63lWxnkGBkS3AMwHA1pWvTXuOyWWcnh6cNHmRaWHoaVebLG_r3zbrNLthKl-ml

CU05: Recepcion convenios especificaciones

1. El Proceso Principal (Caso de Uso Base) CU05: Recepción de convenios de empresas: Es la funcionalidad central dentro del sistema "SYS PASANTIAS". El actor "Director" interactúa directamente con ella ("Accede") para registrar la llegada de un nuevo acuerdo, y el proceso interactúa a su vez con el actor del sistema "Base de Datos de Pasantías" ("Accede") para gestionar el almacenamiento de la información.

2. Las Relaciones Obligatorias («include»): El caso de uso principal depende obligatoriamente de dos subprocesos para completarse con éxito. Cada vez que se procesa la recepción de un convenio, el sistema hace lo siguiente de forma automática:

Solicitar datos y vigencia: El sistema requiere obligatoriamente que se introduzcan los datos legales del acuerdo y el periodo de tiempo en el que estará activo.

Asociar convenio a empresa: El sistema vincula de manera obligatoria el documento del convenio con el registro de la organización correspondiente que ya se encuentra en la plataforma.

En resumen: El caso de uso permite al Director tramitar la recepción de convenios de empresas, obligando al sistema a solicitar los datos básicos junto a su vigencia y a asociar dicho convenio con su respectiva empresa dentro de la Base de Datos de Pasantías.
TLDDYzj03BqR_1z4Ze5TUkabXB3UZqEXbB1k3uLUj3DQTrXRSaVZb53wathgJzW_LiquDMcWFfYnzAIdUK--qOGnJKDVL_eIUCI80w1B4jjqx0dmEwaCL5SzFIT80Z5qNnFu4Ccb85nNTLNWiBalCOaRG0NxM1Atg0IUu1wJQ3xiKP7Jwo_K6NiBssqRDD60krtkc1iXTyQ_QZ-ti6_QviF7TqsxWXzr1VPCIYvtNTrzUlFs2p-Iez65rz-SsplX0t6OkMWO8odgAZDbz4M3LlhWWea0lentX4FeY5t0Kl58toRIPAFZHM6ZOg2ui07-vIg5ZPPyeZiPHkJZN3s_JHoukjgLSM03ZNFaQKwLKCwPAFzcplBNk_Ev3BVT1dRzv2dBTmwxdE8I-pEhpPBevAiyBngjrtkpGTYRFCAac_MwXE6XFzbltdfwCedp3W5EYJW5XrwkP-3xHP5pNAJEh8xeBSj0FUZiV2aw4Okc_p0lQjlrhSFIJCmu7tGK3a-sDdcFeKSp8dICosOSqDdYaHeNiOTyyRgwiQFz07y0

CU06: Validacion vacantes especificacion

1. El Proceso Principal (Caso de Uso Base) CU-06: Validación de vacantes por empresa: Es la funcionalidad central dentro del módulo "SYS PASANTIAS — VALIDACIÓN". Los actores "Director" y "Estudiante" interactúan directamente con ella ("Consulta") para conocer las plazas de una organización, y el proceso a su vez interactúa con el actor del sistema "Base de Datos de Pasantías" ("Verifica en") para contrastar los datos.

2. Las Relaciones Obligatorias («include»): El caso de uso principal depende obligatoriamente de dos subprocesos para completarse con éxito. Cada vez que se consulta la validación de vacantes, el sistema hace lo siguiente de forma automática:

Verificar límite de cupos: El sistema comprueba inmediatamente el tope máximo de pasantes permitidos que tiene asignada la empresa de acuerdo a sus parámetros vigentes.

Mostrar vacantes disponibles: El sistema calcula y despliega de manera obligatoria el número neto de plazas libres listas para ser ocupadas tras el descarte de cupos.

En resumen: El caso de uso permite tanto al Director como al Estudiante consultar la validación de vacantes por empresa, obligando al sistema a verificar el límite de cupos y a mostrar las plazas disponibles mediante la Base de Datos de Pasantías.
ZLNDJjj04Bv7oZkCu41x0F8FYIABn4waI1IXkY1LuhAnDx1Yinljha5G8N7fhJTwh5IfTqvz1Dw49-WZT7Pj1-UlQWvMl3EUxvjlPdQEj27A95DUBks0ByM4NIQAHEpbju2OGYIvL5J37L1j69SmKt92DPE2S7WtIC-cCgPAI7HAtKaitvTB-fg96L5a2cCINLygcOZOsM5xw7v5byog15LGhHGj939IXUQEKo2tLCifBPSMlgIH8U8IpL_A9S1VVuxcPsYDuS6mbHcbGgwPeTfhrWuomr0AantN_FgWMNax3jazXMgZN7fOH4uqZOZUZ5jlj0-3_XhSMlkmqc-luEQgBEBM2WTEXR7aSNgMFdSWAuDb1LngG5RunEebMWAIH4f4CJnY8k89YwLUoxZRTVQOUXviDuDUCAYja5_mMPl7WaUUqf9ohgORTHkq3WQrLMZO3khDHgNod_NQeDiI4o7DFnh77zRzuHeYmthRBmBC2zveDmVBHAghwIibRtFKF8b1ezAihuIi3blLms1JI4ud1em4nIwl3CJCpWAEfZNjG40dJB3v9FUivXGhduhV2PotL1qW6l1bRi1kIc96XA7E5E8R5MPkxjkMntW1CMcJdHADpY_FHAUX-j3jXamREYMUPwcyJUXM-3c4qrxOE_aqweNm-lWTpdl7ew3dZrwUJhPoIVB1slBFTYkj2t5EE8lVxgGR4bbs-aBCa12TpZ0jicMn_RDAQod4ELLimYAYWByyJvbntADa9hNxmfdl_6IceT2uIp4-I6qKHiY1KMazauADEKsZX5VozjmQ8qRN1ChdT8GVuzqQOObeDe8eFEpkUeuvTEm5h1DkI6hCfD_iu0wj5KNlG9ugKB68-v5oaeBQv4UMdBPY5eBiUKKfEgivv5wBgIuvFgITTo8DILi3Ioz5d3NX7PoYa8K3_9jk3FJ5DHJXtYYNt4Ic3IqdyufsdLydkmAyxjZxy_Ffso90fxi_zhhxpjEnVdty1SSaxn046LCmrAwOn87VKC6alOpOZTop7nIHgeD376UBzFhZwnBpjKYXtPQuFzKKRs4oxn5cUpUsQimukKTTKZtTPKsvtQSHRZLdHuo4ftsETAY8tVLaDJt25zpHVm40

CU07: Seguimiento sedes especificacion

1. El Proceso Principal (Caso de Uso Base) CU-07: Seguimiento en múltiples sedes: Es la funcionalidad central dentro del módulo "SYS PASANTIAS — REPORTES". El actor "Director" interactúa directamente con ella ("Selecciona reporte") para monitorear el desarrollo de las prácticas, y el proceso a su vez interactúa con el actor del sistema "Base de Datos de Pasantías" ("Consulta datos en") para extraer la información consolidada.

2. Las Relaciones Obligatorias («include»): El caso de uso principal depende obligatoriamente de dos subprocesos para completarse con éxito. Cada vez que se realiza el seguimiento en múltiples sedes, el sistema hace lo siguiente de forma automática:

Filtrar por sede y sucursal: El sistema segmenta e identifica obligatoriamente los datos según la ubicación geográfica y la dependencia específica correspondiente.

Desplegar avance y asistencia: El sistema muestra y proyecta de manera obligatoria las métricas de progreso académico y el registro de asistencia acumulado por los pasantes.

En resumen: El caso de uso permite al Director realizar el seguimiento en múltiples sedes, obligando al sistema a filtrar por sede y sucursal y a desplegar el avance y asistencia mediante la consulta de datos en la Base de Datos de Pasantías.
ZLPDR-Cs4Bq7o7yO98VT7fp8Nt5i6CRQbhmjq6w3LN8ei411IsE53KKQ99LiKXJOIs-zjSS2HNlFgRTU_K_o2_eJEgHahxzIHBvOv91yxytCezuOoxGjSd5uy0g-P5CkE0s0KVbKCmFtC5KwHGCQKoLJPAaoCDTA5ZBXvGlJ3726YLMG8iK9ZhS8fovgLiYKfomzF30tNBh87CmrBRlZCWEh2roVqOh24wKbQgYtrsSORQvZUoyGs1qIDbhdy4u8ae8CQGKJ87W-vsfztPGbDrcrhL0QZYT3zoiNHyPouJ0B62jfQPEKGjnhp8t5d46Yv1gpDJxmUbIgaX45evnCAMQQfKwHBpOuqMecCmB-u-41q3DQGHfNa1gJrgHLEuxQqNbqNWMvtNKLq1WtetQmFd5vpPCRYSP0enmc7UoUQ3SSymU4UcjjmCiuLOAoyjEM4Z1cZWtzkJBAqr_HecpnbESe3LUIn7xzbiOvIhl9jp2OCBDY-mh2rGQqAtie12YJ55e1Az-ccWl1IFwoa0pF2q7rTwj4GOT1Ctn6jaRtF1XrQyVjS1X6ZJsorKUjIQUnNxRwINj7k8b_jeLhx1VEZIqPniMqHhMH-4BOr8nb1SkPvfATeibTaQPiBvz-tzoxclkUAftq7Gm8VxrpVaPrKH-Enjtn3i4zAuBehD6kRn7R4xTakfFzeMipt2QHBFuKF5Kx_VXiHOVDTYi8gABFEb5ZNsg60Sq7kwKRjO9syuKPs07_JbdogzVLm8KojiQjfr9wsKQPIcN_foExKQSxgHrFMc7GdEp17xQ6uo1yOUlLzs0LXFJhnQD4vfkDx0S_yiNVSaDZhTNT4cDrGhFLwhQZbn_i1hQgtcCHEBD0hgPvTcqXvSwbg3XAc27EkEI9mxDM58S7PT9xeOzMkWS4dbvM4oFNzxGWPBRqa0jcgB4NZyoKiIFezojh7GpSMP_DyIZ-BeQBOJnyT_dLC8QdJx_1--ZYs_UNKNoqr61fBKVZgrhG-I1Zp0gUEmjIWFA3p1V_2CldWWhO89dpaJjqV1LqDjjrc2H4bO8ucOwMFWE2VAUqVFneDLiyfjNmJ1G_A79-JhVTd8aj81CkA5h3dEYx8-aQC0MPcs727-xcKSSE3EpquTPU8Hg2dj5kx9R9nEt5F2XtpnwLMbC4k_y6oOcJPpTSqfnuvEM5p4h6vHIb36grWLS6UX2ZGAy8eqWYOh6gE3VjuYXjFLUXfX2MGUgJYtBzC1zwCjYWsoDy99eeKbmYMuPjyTYAh7h5TVFsbUClY0ig6hhrg_gyzut-UU3mm7TsMTTgjaf_tz__lSfv1ltfuDy_VlrbSxDU_tGww9_wI0_vwTDV40b0OukK-oignIc2-rBGK91WysM1bmGfNvaapmG4tq3qzyJDh0CeFTe1UFhzvotmUm742BVS54pm1zhOe_6cJ0bHmdsBgFBmobLMa0pGHMgvAqi2WJBrdkV4VKClzBtt7m00

CU08: Registrar Empresa especificacion
El Proceso Principal Caso de Uso Base CU08: Registrar empresa: Es la funcionalidad central dentro del sistema SYS PASANTIAS — CONVENIOS. El actor Administrador interactúa directamente con ella ingresa datos de nueva empresa aliada para archivar el perfil corporativo en la Base de Datos de Pasantes.

Las Relaciones Obligatorias include: El caso de uso principal depende obligatoriamente de un subproceso del sistema para completarse con éxito:

Validar RUC y estado activo en SUNAT: El sistema comprueba de forma obligatoria la existencia legal y la condición tributaria de la organización.

El Flujo Excepcional o Alternativo extend: No se especifican flujos opcionales o condicionales de extensión en el diagrama provisto.

En resumen: El caso de uso permite al Administrador registrar una nueva empresa aliada en la plataforma, obligando al sistema a validar el RUC y el estado activo en SUNAT para asegurar que los datos corporativos queden archivados de forma verídica.
TLJDQXin4BuR_0w3SoW4R7OtTk8OOxAsrxJG5fDD3eL0aNULjOXMSYLjKgSKSkcjj_POAFJQOu-zfM-I9-WZT2J_r77MknTfVZvzyyr89zeGPOgSLolFu3cPCCxG05hc4qKqp85gmxZKSCrqGJZLS32iLlGL4pEYI0vwIb9vmqG6HXLqqwDa8T94Aa4L-ArD3qcCLB6PSmhaXk9HcBVfdv3aAbkcSwbWRnJQ_t6GeeaX8aEC3zKAuDTVPmsMMS6eEMhMzw9Mr8xQoo2fKggM0S7W86fvcuwpAKkk1DKQWeLv98KfYRRccDrIy9iR1bVHHFAqMlduc6oXQKBqRgh1STlh7zVtMiDm60KbLFr-StGKb5Fr6wqdP4VksoORb9Erjb9YtQwUQqFpjzWn9aMlXqJye_OXYkg7_S7nu0dJaWmlEWnQ_XR3ahWLvItftB3i56vuq6fw7lRuy2WAoeGBFVJlw76PSELTtY6SexeWM0lJd0ccZSBxe6g0TyTPrlw-xNzAOKWCtYPSZ8acmb3jOlj3w7PZPYKXlPw5_J_VjVXD3ECm3b-VlGXZUBZx2j6hyMaKXt5j9Sngm6g3yxhNlX2dD7DS5D1yfgWcxfJ1kTVUYXynxiBcS4quIt5rUZwu4FIzvOBqW0em344atZZ25uKbneSd7Tm27b8zupH3m4kfye8JnIIMVI5I9u1K6H7ibYIOQv-L5N1G1knqTd92lTvpPK07Oifful91pXBsvvT0YikognKNr6Zq5cmxSF-JYOGNARt__TWPb3hjETYK3eGy9md5CvYmXP35GVYkpQGYXbqJoqr8L4gnR6f0Ngvb_llzosVOtnzZAwL8cSlixEzRryFT3uWugbKuNKXXnMO9pWvgDA60MtmsPrJbJ2_69RCFCG8qRBg3-FR9WajjIj5VabNhuLr1KxBM1fTpc2vVUjnWWoa7lPWzHASY1LjFjNA2ooB_1m00

CU09: Actualizar Empresa especificacion
El Proceso Principal Caso de Uso Base CU09: Actualizar empresa: Es la funcionalidad central dentro del sistema SYS PASANTIAS — CONVENIOS. El actor Administrador interactúa directamente con ella modifica datos de contacto o razón social para sobreescribir la información en la Base de Datos de Pasantes.

Las Relaciones Obligatorias include: El caso de uso principal depende obligatoriamente de un subproceso del sistema para completarse con éxito:

Desplegar campos editables del perfil corporativo: El sistema habilita de forma obligatoria los formularios interactivos con la información actual de la empresa.

El Flujo Excepcional o Alternativo extend: No se especifican flujos opcionales o condicionales de extensión en el diagrama provisto.

En resumen: El caso de uso permite al Administrador modificar los datos de contacto o la razón social de una organización, obligando al sistema a desplegar los campos editables del perfil corporativo para salvaguardar la información actualizada.
TPH1Qzim68Rl1l-7Z_GMIB3Tk4r22BKJ1mRR27Cx61I6Agkkg2q5ILxNZa4lk-ss7GU3NNVSSRVkd_GNx2TCKX8lIHtdOlHztwj7xoldH2eaL5KMhYElALiWWKgGLoZZDvJbe4H5DYk2Lop3N30Ym0ytAmWhBb9rMn10DqJoSclk0k7hV3LSS047iyZyN6TBd625MAuLFhWEw2UkfoQhgM3Mc_Kw1qcOz9F-gecBZ8XLGp0vJ49lit1wHV4r8r92i5oUSQOQkiroIky8-BsD1NkU2rvahlDn6xQI12Ev7pKOzBruq3a8fz4q2HfG_RWtEmwQKVrk-0HsPfzTsA0PrgmrWer6ybOgKhxLUL7EncCDuX_tZxIfVXHF1fCdf0qJNd8KXFuEOKFV6dd7EdjLzXetFGnxdgSpFZfEWYRZ8a_NzsJSP5npodkCiwXBm5QKbPHHgOJ-6aGBa0IxKjTZatz6O8eKb-PbZYHYYaZR6qzXD4gfiGIDnqRs__rkfMzIc4TfzFBqMPJ2u_rNI5xCNoLfbBRMngmlM6jorl46vop2ga85lKC2IBaGH2AxpUJC6-mCJ8bS52JNZPTSb5M11EM0EJjdXU6qjEzeJcfKBUt3a_nsL5yJGIyfrgfK3-Q2PYZJXpvd69KBhKWoghHHjMBGf6ZjjIv2fpEsy324k98OmIr8KX2CTIjQ7z5rR4ktErv23k7X9sMug3Boy7kx63GMpIuwYI7Kzkc_cTo4keoisDZATHXN10JDhnJmozhQlz-_V8PsUwxpuooZcFxvnORjjYaztl-0vxM45hmWGDvhUQfJOa0AaCiRq3NTTkBR9wF5fMeMgnFQWWF9cVbkbaVGBkiyXRrFfObHgnEMWS5tdHFzMfN_0000

CU10: Dar de Baja Empresa especificacion
El Proceso Principal Caso de Uso Base CU10: Dar de baja empresa: Es la funcionalidad central dentro del sistema SYS PASANTIAS — CONVENIOS. El actor Administrador interactúa directamente con ella deshabilita acceso por faltas o término de relación para actualizar el estado de la entidad en la Base de Datos de Pasantes.

Las Relaciones Obligatorias include: El caso de uso principal depende obligatoriamente de un subproceso del sistema para completarse con éxito:

Cambiar estado de empresa a Inactivo y restringir accesos: El sistema modifica de forma obligatoria la etiqueta de control y bloquea las credenciales de la organización.

El Flujo Excepcional o Alternativo extend: No se especifican flujos opcionales o condicionales de extensión en el diagrama provisto.

En resumen: El caso de uso permite al Administrador deshabilitar el acceso a una empresa aliada por motivos de faltas o término de relación, obligando al sistema a cambiar el estado de la empresa a Inactivo y restringir sus accesos globales.
XPJFQjj04CRl1h_3uDmCDf9Y9uun9h8jGw4j9aeAXK1PhoRoDj9ks5qx9AMGIs-zjST2eTSUS-mjUPCyGH-Xk-i_iHsPIXUnC_lDRxvPxR7IHEffdfLBwfBnAo993cf24d7DU0fQJd4z8iMK9rH8ZXByvdg4K2rah6yo17ADIkGR-yQ4NgQBpPcGi3SCxLikROWZrOIdHk5JkGJcwQrszHUxWc5ZsAZjHSse5RKMIK8cA1S9GNy_QdhhWTC9evSSbO9WlZmKN1Tas-MOtIBuZRK5ryzOP4cvz7aJTggG4hKRDJXgURsZsbvp40wYe03LxpM6Xq4ngbzlle0TkcSRDYY6jMk5O9sEkb4QymzcNapmRjU0-8Uj0sEg7_RwH_qNf0KxlEWWQFfRX0LvI-GjwznHsMdSOB_Py3mpuuF3A2WoBlHCVCUCYumhdl8Eunpg7B0I9ZdZJ6bf_WPP0QB0hQpYFJl_1650j53sOqGKuHgLo-qDeDE9cRM4TBjMzlbyL-BtCOp2E7nx-YgCuUdkEqHlHYTH7CQLfJ7B0rRfdzLyxvn76JF5YGJChoGguehqptnlA_qTIdR1g4aaPerJHWpQEQU2pv0p0pfZd4upqzESCwJQXnV3sn8TeBhAC3MYHiGqiTAyO38db3tUSsl0c7maIz6WIDJPwro4MgthyA4DCMP8gKaXo-R0V2twBPTSLhtUdQEsuU6twI2R9lZmPpCO50Pj8JECDfmWoTWjSPGWWF496RECwGL_zdYV6jyi8HSQGR9qea5Sh4p--_FRLwXMHsQEWYVCxMfNgpRqTFSBNZ_J9pX6G7krcaijdHyX0ZV01MYqT-VwD5AqPyR-5MmcLDtAESaVNsmneVJ_gb6IZvcpp5HCR6DpBTEZqPMOYnbBB5G6QduUJH7a2TWsowLZypdD_m40

CU11: Consultar Empresa especificacion
El Proceso Principal Caso de Uso Base CU11: Consultar empresa: Es la funcionalidad central dentro del sistema SYS PASANTIAS — CONVENIOS. Los actores Estudiante busca plazas o convenios, Director revisa aliados estratégicos y Administrador gestiona el catálogo interactúan directamente con ella para leer los registros en la Base de Datos de Pasantes.

Las Relaciones Obligatorias include: El caso de uso principal depende obligatoriamente de un subproceso del sistema para completarse con éxito:

Generar vista resumida con convenios asociados: El sistema construye de forma obligatoria una ficha con los enlaces legales vigentes de la organización.

El Flujo Excepcional o Alternativo extend: No se especifican flujos opcionales o condicionales de extensión en el diagrama provisto.

En resumen: El caso de uso permite al Estudiante, al Director y al Administrador buscar y revisar el catálogo de empresas aliadas, obligando al sistema a generar una vista resumida con los convenios asociados de forma inmediata.
ZLJDQXf17ByBliCVSnCKTwFHY4XMNI6N4hf9eH0euynKXypEc9dPfgOKSkcjj_POAFGMIayzzXRV94_GH-ZC-14rAtIzxFu_VnypdcY3bCbINYpeAoQcIA4Kz0GHUSF468pAw6P6oKmGB9MW2eB6PWPX8rLYPfm2kg5Qfbjz8uIlnijcBXKS32FtAnQsXbDia1ZR2H-A1R1FRztLNtQ5m_gmNZc86t4hRYsBf29KBGl2_c7Sg6qcpYSCNmcgDOIBy50AarFjmWcxfH3KDmAUpqXoKYnyt0QRQOgHtWyrF6xLUiULWyOW6iHX3jIWLnysmtoeGRNn3EpGFxjWmtomBfOBhDFHCsre-iRwnQJeTYsGeDawig86KQz_t7-6DAUZ5X-5ZM07OKxT2lAETFwex1LkSDYershMuwDc7EO95zLiVe_7USBbkxn7E0zr0R0KaPG9fesojq6L06dmaNM-v_md50R8IErUpf16mb3jQti3w7GIvYH1tUwwQHc122ColqyPbhuwcMaNsMuf5fwkH2bvdS1Pb4Glpa-Z11xllaASd5yCJcqWJaehELV7ijI_g0J1fNX9nvw10gfDHfZ3vnVsBu9Wf-KqdKfbNEdxAIMCsbAONGgivlU4EOfegkJ8Yh4W664Jm3FNTsQ-GfmHDv9R82FcFeYLwbAaoAZvBvnn1E_OcAvWsQ5Xtb3lYvSVAfMkHmzjI2Hdc1ba_peyJUbSU29QBFYwQhMx0Dk6XvzCO9uH-l1dEndc9jsgbJDscqqhATWj0hAqd0FYMIhaHhtrlGqHJn6cOXlOL5fa764s_oqS7I6jm8gD9mRasxKXVxz_-GpbyfcrNWh2V7MxN7QfnxiV4FCDWdRgo1Es2Zj1cTEJI9W1pj8fPmhi3E0MggBN6TCB5zSdJrVTL3_vsoUtqmByZwNN6ILhPejr4-IyDUx3tV4LLMKNK470CIqMJknhblu3

CU12: Registrar Convenio especificacion
El Proceso Principal Caso de Uso Base CU12: Registrar convenio: Es la funcionalidad central dentro del sistema SYS PASANTIAS — CONVENIOS. El actor Director interactúa directamente con ella formaliza vínculo interinstitucional para archivar el pacto legal en la Base de Datos de Pasantes.

Las Relaciones Obligatorias include: El caso de uso principal depende obligatoriamente de dos subprocesos del sistema para completarse con éxito:

Verificar antecedentes de la empresa seleccionada: El sistema revisa de forma obligatoria que la empresa no cuente con restricciones previas.

Cargar documento digitalizado del convenio firmado: El sistema solicita e indexa de forma mandatoria el archivo legal en formato PDF.

El Flujo Excepcional o Alternativo extend: No se especifican flujos opcionales o condicionales de extensión en el diagrama provisto.

En resumen: El caso de uso permite al Director formalizar un vínculo interinstitucional con una empresa, obligando al sistema a verificar los antecedentes de la organización seleccionada y a cargar el documento digitalizado del convenio firmado para su almacenamiento seguro.
TPJFQnf15CVlWl_3Gs-2ucvSOqGawxgsWRO4DXOAWJBEZ6PmToRCp1AIKiYbjzxQOw7GQuyvzfRy9_aB-YTqPbojcdMzxBvVytdVzyPJfP7KUPPMAsh9-3MIA0DrXOYuONm1MkPqsoD5pWaMabC9Nh3jGLWBcUZRb0AweKfaEtapX9UB8ZaL4kgJqFwgbPtY56l45wR2fse5p3FQP4L5bZ_fJ3hDUXp4lRXN10b9g2m2_EWe3jhRZeihXfUSAWN-oZmHN9T4MtF2xYXudIs3wsScKbAjVDw5pHN5I1r6zKzwxT59inwCmt7ibw1weyxas2z7zLh12zY9U_PX_N9OQoi56mpKhT8q-sZcnGGV3Ws8Tzph6b6zS1ITH2z8IpBQSTSFl3t2ahWryfvqRbKE2ZS-2ZhjjfbnzpZsouGBsyP_OCPbmfLF-O1m3dK5M0j9nZXJMfhR86k053ZBnXyhdHE6kAREQJuthf5T3K9XZBHGzkKSAHkeNEHe38D1mgnQQ3Yq9_vV_Lho8O7pC0dVNPo52JpVVuSukPYEpumXJcfhsTRhLukcJS-_v27MEKhP7P90Tx6YwRhNJSvhD6CfCnSVigS7agSEyP9JmZ1xUk2MDteFju2DEBQXLUzOU_1Yo8LYJXXeDeVkEEZ3Mq7Od644n2c055jm8wEgLenCsu4RS61yBcI6LWZNL2h1aVbRSd6jrd05q8V7tupZD2VqyK_XjDMCf7rubID9462KpPWvb7AWgQqqPwc5v49Ja6nnfK7CDxhy_VdjApGQvsO4WXSAz1iDwtg-_mLnkYMeKMP6xRUHJj95iHij6-lYVtonbOJIfQNUxFL8w4vjgkpDM8b1a2bAEG7BNAsScjSy-mS0

CU13: Consultar Convenio especificacion
El Proceso Principal Caso de Uso Base CU13: Consultar convenio: Es la funcionalidad central dentro del sistema SYS PASANTIAS — CONVENIOS. Los actores Estudiante verifica vigencia para postular, Director supervisa metas de cooperación y Administrador audita documentos de soporte interactúan con ella para leer los datos en la Base de Datos de Pasantes.

Las Relaciones Obligatorias include: El caso de uso principal depende obligatoriamente de un subproceso del sistema para completarse con éxito:

Desplegar vigencia, cláusulas clave y descarga de PDF: El sistema muestra de manera obligatoria las fechas límite, las pautas legales y el botón de descarga del documento original.

El Flujo Excepcional o Alternativo extend: No se especifican flujos opcionales o condicionales de extensión en el diagrama provisto.

En resumen: El caso de uso permite al Estudiante, al Director y al Administrador verificar el estado de los lazos institucionales, obligando al sistema a desplegar la vigencia, las cláusulas clave y la opción de descarga del archivo PDF correspondiente.
TLDDQzj04BqR_1y6vsQmiMGxSOmnaIqPSYcXIWw5GDbeD_QIrQxPNJL9Io6NtdfhZuL2RwNqb6DlyJ_9B-XFwApyKTcHPJ3Il9dPD-_DdXXBjCrIKQsO6oxdH9CKp8nGTSlb5ApEM17HAfCqKLeo3LwtY934AXtRUy60t3AZqgswAvBSJ5V5Gcauc0JkLwriDMU99NAA7JvKAu3FQ5CrNbNvaywaqpY8kb4lwgsIbAPChnBySJlgjeh0-OmdDv8P0_uoF57IbcIxSCpVC_0wXK0-pvKIj5hvk4qsComXPZzL_xZN6Xqt3hfX44P-2LLlr9aS-ULKlMRt1Tb9_koIzSl9kbWfiS70t1lBqhVe5rToE4GYtb7l44NrWj7uUFo2QKb5AphqkzuEmvAyDUKTwV9LsIjSsEvsMYtq-F0eyik42rg8x_6uJBXob_S8brDT4go5t6saqZKW1l1Z0mGqvP8Rg_6QBD4yii7ZRCxqEsvM87vke97R6SeW95OPzt96396McJnp5C9W47Cd8naE7PN_Tw8MludXB8Y3L-UdGGpF3ryXYiylmbCCH75jhUTwBslZYuRNlfHZ9Kqcy983CpQZt1sMdpM-yDex9HCkS2ODYU8ouPJX7oREbRwKoUAHyga21MJEXE1KBHa7YVNWXVKxVKDcve9D7OUxEQES8GUulqJ7B2heL9ZdAYn-aqrNlwnhxWuw0Ot6C1y0-h0U46QeczAS25mmGXS_KvweQYLtffW_oan2YaGIbI8xYxbeL37pDKCF2H2HfHBD8f0GFSMq76usXylX-_3q2-KI6MLFVxP1lnHq9w3HVOZkK6tSXdmLK0kT9JPpEsNSc58XDysdCmlgUkFMt-zVFaEzVePxeIJb2Lyyodwzxg3dXnyGYOBDAEmLmqbH5vICIM02p7AvcguWB_hsoRLJnfRsYncW1XaH_3q1GO3BQwLJagTXUqk489JWM_5SRCua1JT0jNA2hrdw3m00

CU14: Dar de Baja Convenio especificacion
El Proceso Principal Caso de Uso Base CU14: Dar de baja convenio: Es la funcionalidad central dentro del sistema SYS PASANTIAS — CONVENIOS. El actor Director interactúa directamente con ella rescinde acuerdo por mutuo disenso o caducidad para modificar el estado del documento en la Base de Datos de Pasantes.

Las Relaciones Obligatorias include: El caso de uso principal depende obligatoriamente de un subproceso del sistema para completarse con éxito:

Inactivar vacantes amparadas bajo este convenio: El sistema da de baja de forma obligatoria todas las ofertas laborales ligadas a dicho marco legal.

El Flujo Excepcional o Alternativo extend: No se especifican flujos opcionales o condicionales de extensión en el diagrama provisto.

En resumen: El caso de uso permite al Director rescindir un acuerdo legal por mutuo disenso o caducidad, obligando al sistema a inactivar de manera automática todas las vacantes amparadas bajo este convenio para evitar postulaciones erróneas.
TLJDQjj04BuR_0w3SmWOR2p5JXnZJ6HRXa19GfK42e6oNasTRQJTT7ULa9H2BhtrrXuBXLvxxB6tz4to17s4pigsuYIoT90qFzzyyyrezunbscPfKgsO2o4lcMOfc7CMgsiXPs1rXgiUhJ8PSwKbQl0wgnx6hTAHlKaGs3KQbJx9cp9-CLia9qh3nYHmTxNo11ovPN9621-h5Q1hM6ID5bd-f3rfDpR2JjWDkuiWfMFKYm1_j1LsMgkEutF1BoGQ0_xSF57IbaGxSoHk4RpsYY7lPwgIk5hvz9HiPf0pivwglzjj3NSR6vrnC0xz4ghUi3tPySkfUitE2xAJ_7fErYydwsobnFfzSsCifczfNaB9mO28U3lTRHBL2uQZtT4BfYKPhN3RxtZF69R4BIa_aovVbRN2ZRSwxLQBPhoz4_fbmWKjyg-PSPbmvLDU8rnETKwmDXPk8vMk0JD07uKZY5CXXR6QVfEvDxSK_g5RZ1XXpAmoxkM86IOjcZnsE8P-Fn9EApOOk7gFYr-BtaHm54J1mV5-4C73tJSO7HwSXWVxXr5jATbozMgZauRNFfElSPQJqS2Ll48fL5vdTB9SvIBXL4YU9HGOAvwbAAq25h_Fw7acRm3fB9WcoEdVlX8pb5omUNFSUl1Yl0kjI1TeD0PvDUZ1lZIeBGEPuPKg-43AD5VLIYxJQlYIEkr4XZfM8AInmcQSIZ0wa_AmPdCmvz23-r_KGPB5UFzduNHWf6WFWYHb72LxB8eoRubGDqzTFnOt7MEfB88MitCBwbsXqhyVNxz0lNv4ir0o5bpy_IrxzRfpFTpzX5SCCBtKQ1XfauiOCvhi5FCIciwkUIDaTMKJCFC1Dnr03lBziuDNnfRYXyaZxmyP4ao1I8sGB9J1m6J5P0WOPGokcMfbZrwpz3y0

CU15: Renovar Convenio especificacion
El Proceso Principal Caso de Uso Base CU15: Renovar convenio: Es la funcionalidad central dentro del sistema SYS PASANTIAS — CONVENIOS. El actor Director interactúa directamente con ella gestiona adenda del convenio para actualizar el periodo de validez legal en la Base de Datos de Pasantes.

Las Relaciones Obligatorias include: El caso de uso principal depende obligatoriamente de un subproceso del sistema para completarse con éxito:

Calcular extensión de fechas y adjuntar adenda digital: El sistema realiza forzosamente el cómputo de la nueva vigencia y asocia el documento digital respectivo.

El Flujo Excepcional o Alternativo extend: No se especifican flujos opcionales o condicionales de extensión en el diagrama provisto.

En resumen: El caso de uso permite al Director gestionar la renovación de un convenio previamente registrado, obligando al sistema a calcular la extensión de las fechas y a adjuntar la adenda digital para lograr que la vigencia del convenio sea extendida legalmente.
TLHDQzj04BqR_1y6vsQmiHGhSOmnaMMv14eIggHG29JDxaJUHjuDkoldenHowQstzbWezDfZZxsb_oI_e3-XkxBZs8uiNLOpRzw-URFQVMs8ClaagrRq9HTNH949w35XyfgB58pASJcZP2uObKgW0YzOpX1gf4hCROP0hb7BoKhTEQ6NwRmuamgsHg5xgvKLSgI6YDGoVAnMm3w3HLKqh_97xL6xiHK7SIVkp45ICLHpW1zjnq5hEN4ovlHIeDRWpy8ZAKm9seKJVeVWjPS2HJ_dCcFLogTLiRb6IlHcgVvUfpNOQsm5mt0O-oLIlK5xjEkNI_MQmGkne-9P5-kNYtMnKc6zdhxL1YVlxRou5Fs-5UBjTdQigLuuYFQY5qfBAbhnZXzuQmfBS4-IrwmhZif6uuRRGRlLiZFUsOtzCkF2birlc76PSULJtc1S8NKci3RaxaHALGEYmNui4WCtU8Om94PgjpWccWY3ka0EXj3h9TnvGVfzn_Tyi6l9kmIEmoGyF3a84tYy_mRHqU7R-F3WAAazMV9qj6hHQSCBpiGR579A550ffYYuB7Q9JhrW7KuoccSMY3S6XUP_VmidxWBfcEWpSGk4VSY5_T_j0WKZm7ZA3SaAlf0Q3rxCS6w8RHuQZNwnANJX5MgN9WiUp1RYgfK2r6psPvHTUFZ51SroXWz_vab7PLtgEaHECdv7u0eLbqmwlLCRONW76QOaSxiBQH0KJyS6vCMYyNy_ldw1UltOcYi5uzIrswtNNUhn_YV4pv8iwJa2kflEtZ6fdOooznjSAPnoCa4xkAQhAYg_VtQSKfjIqjS4fZn5GVbgqvPyPZhZZ5Wokm2dkbhPjyjyyXy0

CU16: Registrar Vacante especificacion
El Proceso Principal Caso de Uso Base CU16: Registrar vacante: Es la funcionalidad central dentro del sistema SYS PASANTIAS — VACANTES. El actor Empresa interactúa directamente con ella publica requerimientos de pasantía para archivar la oferta laboral transitoria en la Base de Datos de Pasantes.

Las Relaciones Obligatorias include: El caso de uso principal depende obligatoriamente de dos subprocesos del sistema para completarse con éxito:

Verificar estatus activo del convenio de la empresa: El sistema comprueba de forma obligatoria que la empresa posea un lazo legal vigente.

Asignar estado inicial como Pendiente de aprobación: El sistema otorga de manera forzosa dicha etiqueta de control a la nueva oferta.

El Flujo Excepcional o Alternativo extend: No se especifican flujos opcionales o condicionales de extensión en el diagrama provisto.

En resumen: El caso de uso permite a una Empresa que cuenta con un convenio vigente activo registrar los requerimientos de una pasantía, obligando al sistema a verificar dicho convenio y a asignar el estado inicial Pendiente de aprobación, quedando la vacante guardada a la espera de ser publicada.
TLJBQjj05DqR_0yNPn4ms5YAvJZ6cCYo38LIJ9K42e4obYRo46d6dHav9AMGJNVTjSj2eTlILPVT9N-IB-Wdz8vaExOZovlnVPnxxZaZdIfDfCxIf5fHrupFYIGfg1c9n0tZCMYPqSsC51cFGY4vbM0vcnaIQY43VPjG83TKYNIhRqh2wtZPd0W91sFN_AgLBN0QQi9ZHFXOhG0-mtMNj-oon-rnkt7WEtxNxowBX8oeN1ROtf7lj3OJPpCMNdEg5DX5U2ouBgasuO3TKR3Q6u5ydwb8echbqpRPJD6GgFrKxPDkQtZIE716xiYtIwXQm_Rus2wdQZMT5sJ7-RDBrYudQsAbnFfzTQiqJT-ZNqpmmG29MCVT3efgkKFln7l1jAIZvNTinzfXM5AtehmZNNvLzWetEdBQhHPwt3dsxJBXt1RcztXS9bovotk4owaM16j-EfTKaHeG1NXUnuV6zuZ2Y6YXp6525E6QghnoE89-Fs162Z8O6BZdUrqBtWKmSGFtpTahDu2d-szmuNhupmzgAq5M5wlcdJUipYL_IsC4aqJ2WeHcJ3x5ExSwE_KNLB8h5c8XnPTQPye8pHRYaaSqWL3m1ULC6Bu90Rgncnjg2rxOjuFkAXRp9NOaW74MCc9WKnnmEA4yOXJ96NWobm9VUFRuXn-k1jXb0tAnKLbeD0RvHj23IJPDS0dy67p8SA7Ke1OgptEL7t-JQYMlRJO71VKUFFnYF4ooY3xytKxQfKap3ctgWIl36LiG45TKQeAwJ8N4fL1jhXXwpOXXo0Nk9LayqrYuLlxVZwzVe5wVeBi2by_NxTNh9lLq_nDUhpL6xbCAcfflPiQVZLYmE5UiSAbf6lFcxvyDh51w7-xo7W0A51cXYlk1Hv8xg-PKcg6WSE2ya3CYY8yUWTcbMZd5OvR-1m00

CU17: Actualizar Vacante especificacion
El Proceso Principal Caso de Uso Base CU17: Actualizar vacante: Es la funcionalidad central dentro del sistema SYS PASANTIAS — VACANTES. El actor Empresa interactúa directamente con ella modifica perfil de vacante abierta para reescribir los datos de la vacante en la Base de Datos de Pasantes.

Las Relaciones Obligatorias include: El caso de uso principal depende obligatoriamente de un subproceso del sistema para completarse con éxito:

Desplegar especificaciones editables de la postulación: El sistema habilita obligatoriamente la interfaz con los campos modificables de la oferta.

El Flujo Excepcional o Alternativo extend: No se especifican flujos opcionales o condicionales de extensión en el diagrama provisto.

En resumen: El caso de uso permite a la Empresa modificar el perfil de una vacante que le pertenece y que se encuentra abierta, obligando al sistema a desplegar sus especificaciones editables para que los requisitos u oferta de la vacante se actualicen correctamente.
TPJ1Qjj048Rl1h_3uDmCDfPYnOun9h8iGw4jeKeAXK1PInDdYRJhxguQabB8fRVUscEXq6kFFVQMlacUe8_GMLbsRKUMBgkTcN--_MVHYJPCcJnBwpLzpSM2APQ1lcA9lE5Y3aRbk1bHCXT9B9L01Owt6M6naIeojoa2kq4jiwsw6OklvsLnAXKSJ7txrcjRuXWR9kQayA5U0th6wwgWh7AdtMctTH1wOJ_ibqbI9QZA13Su3BtEPk3iYiVN0hK6TxazbS9KPDljYDyXEDsDZU8yCvaczTh7RTXSOypqVbJtkDyP7xSEl8a_2TqAL6VSdVRSQbIdxJs1dHRFBgnR3MltAi66Gtsh3MPlQLvSYj68G9nU_uXCTVnnS1my8Qsew8H7hkVi45RahP1th2kkobxZ9eTUjzEX6H_rGhVAEBz3yJqphZAkUifxZ2jGbu2DC5ierAm1J0Ejr_jZE_S4OSACr7PnoZGJ1dMHEPx0S1XnQmKRZQpS_tlTYDv4SEf7_ikpPtu4Z_TVuRKVq5SODLQ6h2vM8pXlERqBuSScPoc_OmhUizZsATe4vqvlfs22Uf7Yd19fWJ6_v36BQHIeBmGctB1PYWLloc0XjSbJ2l_v9GezQkF0ancMXj3feTKQ5KrX02zaKeZ30jKbJwraYGPinb4PLgyLgUtsQ2ayW8UVNCHfdk33xp9e1Sci0Rn2rB7YCp9rvIWHbegslP2ahFZyoe2yN9_yx_Sldw7PF2LxfKXuSPH1isb3Z_S_uFbQWWH9crWD2epfpyMiFYwd2xVa5lq3L-HjMrzeVFjarScdQda2LVWkvvfRvfp8RFasFD1Oij8iGSee4h27gTTEQ9bd_m00

CU18: Publicar Vacante especificacion
El Proceso Principal Caso de Uso Base CU18: Publicar vacante: Es la funcionalidad central dentro del sistema SYS PASANTIAS — VACANTES. Los actores Administrador aprueba vacante solicitada y Director autoriza publicación masiva interactúan con ella para actualizar la visibilidad global de la oferta en la Base de Datos de Pasantes.

Las Relaciones Obligatorias include: El caso de uso principal depende obligatoriamente de un subproceso del sistema para completarse con éxito:

Cambiar estatus a Publicada y visibilizar en feed de alumnos: El sistema modifica de forma obligatoria el estado de la vacante y la despliega para el alumnado.

El Flujo Excepcional o Alternativo extend: No se especifican flujos opcionales o condicionales de extensión en el diagrama provisto.

En resumen: El caso de uso permite al Administrador y al Director autorizar y aprobar una vacante registrada previamente, obligando al sistema a cambiar su estatus a Publicada y a visibilizarla en el feed de los alumnos, haciéndola pública en el portal.
XLJ1Qjj04BqR_0-3SmWOR2p5TXnZJ6HRXa8f1YM5Gg2ij1jxYRHhTbSEIIdaqbjlxR5GwBN77djB_oHVq4_eh2GxjYDJwIBDl9bvysPspxKXogH9NAte6owMH944z89GUSl578nAsRP7oLJGI2h153YTRG-9Z5I1kOiPa5kcPR8J5vBePbu4nrB1qTIpRxMoavn5XeWvPlXGhG0-eqtKk8Xof-rfkt7aT_oUtoj0Kb6c2e0xFl4xhMt7nO97Du9f3MvkdafXIj3M7F1x1avxov3r4ygOLYiVTycccaL47wRgdlLQexF6KMVYJNotXAepQazFtNAgJhFpWkmqU_R9kkLahQsKs62WxxHXoNkS5vTYE4GYpcclYw8wtcXyDdx1j2IYvNVTZhF7i0ItfhmdNROg1uMRd7JQhHREk7lgksN2UItq7vXncN3bKpuWN4Or9rZpQC85rqRXQL0r81eooyO_uNPZ2nV-R1mZknYKmOGOgUt7Z6WY3DCPSZI1mI3WLYio7DfwpujV2zu5CFC2xyt5Ao-0fuUlyDORuvyVrDQAhJUlDhviEBqhCKl3c4T4mOf4jafMP7pfzFRX90avmXWUUPDg871SX59oV2NkOCKr3tdCxor8m3LZr98dSPe8cNFt8kF0YqaNicNgGACnpAf37xmbNXyXMHC3BR4QDrYlMa6zTg0fAeULOPbJYlYVNm8IelaAmHcesHpczVlm-9EBA4ufU_nTE6qg5BPl4IcnFMpQeOJ2F9OXYMqtCG5vpPGXbh6Go4hn-SAWSQFPt-zVFaEzFiEnI45vHgLVhrlNqyCFUFtS46KXWmK9yJRKd4gymURvlc0VYgquIHZ2cZOoY_xsoUQLslmlCTCvVLm9d0IBOIcHSju0hXIECAKyMobCpWG5sqcrSewVQV8F

CU19: Postular Vacante especificacion
El Proceso Principal Caso de Uso Base CU19: Postular a vacante: Es la funcionalidad central dentro del sistema SYS PASANTIAS — POSTULACIONES. El actor Estudiante interactúa directamente con ella envía aplicación a oferta activa para registrar el emparejamiento estudiante-vacante en la Base de Datos de Pasantes.

Las Relaciones Obligatorias include: El caso de uso principal depende obligatoriamente de un subproceso del sistema para completarse con éxito:

Vincular CV almacenado y generar ticket de postulación: El sistema asocia de forma obligatoria el currículum del alumno y emite el comprobante digital del proceso.

El Flujo Excepcional o Alternativo extend: No se especifican flujos opcionales o condicionales de extensión en el diagrama provisto.

En resumen: El caso de uso permite a un Estudiante debidamente habilitado enviar su aplicación a una vacante que se encuentre en estado Publicada, obligando al sistema a vincular su CV y generar un ticket de postulación para que esta sea transmitida con éxito a la empresa.
TPF1Qjj048Rl1h_3u1m21XjBiHFR61DPbY5G4bCbWKAWZAMjlOsq6tPNITDIoAMttjfZeT1hwQd7tf8toHFq4JehEwxjoFB5sfdvvvj_LeVQe39PcfHB-fABArIOWfvXB6-uc89H6LkDA9c9E99AC0LEQpM2aP4gDBS90xnXMgPhTHECBgUBuaGgs1bvzbSkhOcpoA2OaiA7SWde6Ioh_4MLEsgEchMTe1MqW_OYIQgOgKM2w-y5hSPgu7J6eql1j0PtVZoImXHas-EGlsVWD5SEydacCedBfO_hi9bc4Uhjg6wdtHXqQZkjeJSCt09KPz0S7RZ5g4wzzGnsb3-Ri6unh3qh1ElrzAqsB7rD--9IzFi4uXoqzybKnnlu7VyPQK558zXtMyu6OK7U4_A6TVbLsMhSSA_LR3Hen_i7WLjadDUW-9OT5nbNlEKjnkMeSy1Ae4qMSnI6LG0rqEioDB2hZnaCqKXj_unHsqITPmw6qEk5tBg1_RvL_7-rA-6h4CPUw1sV7daXFDvzXV59U7hsmlEFJew3iF9apDC5g_XdDQTp8SQIS19KW72DqPBAFtCw6mNdN4HvfdyEcAGOCK7VCznUY2cZ3vS2XlnYnd9VpLKZ_l1Rv7fUP1nujik5CMG1r6hzl2bq8H3N3xyGy2hXqLo2uEGRfWpQ9VDhB9Vor7gzFnVkmlrFeakocDt_MGIj83dMXPTiIfuf19RIHM5lCULC60bikOVQOdBB8gHXeFXqPgZbqeQ_txzyXcfrJ8PB4VCSgbkjsj3ZtGy8aXKrcd_2x3ivCiC9JxZ9VO9aQJ4maIVGyUuuczWvOzojMxbSyjidsumyBEps0jVy9INIk-Oa0UmTfvk3ARDDq7QaeHNJIDfCn62dAvSEwM-M_WC0

CU20: Aprobar Postulacion especificacion
El Proceso Principal Caso de Uso Base CU20: Aprobar postulación: Es la funcionalidad central dentro del sistema SYS PASANTIAS — POSTULACIONES. Los actores Empresa acepta propuesta de pasante y Director valida y otorga firma final institucional interactúan con ella para convertir la postulación en una pasantía formal dentro de la Base de Datos de Pasantes.

Las Relaciones Obligatorias include: El caso de uso principal depende obligatoriamente de dos subprocesos del sistema para completarse con éxito:

Notificar preselección interna y generar flujo de visado: El sistema comunica de manera obligatoria las fases previas y prepara los documentos para firma.

Asignar estado final Aprobada: El sistema actualiza obligatoriamente la etiqueta de la postulación al nivel resolutivo.

El Flujo Excepcional o Alternativo extend: No se especifican flujos opcionales o condicionales de extensión en el diagrama provisto.

En resumen: El caso de uso permite formalizar la selección de un estudiante a partir de una postulación activa, requiriendo que la Empresa acepte la propuesta y el Director otorgue el visado institucional, obligando al sistema a gestionar las notificaciones de preselección y a asignar el estado de Aprobada.
TPJFQnf15CVlWl_3mnm2WhAxqSI8IDPrXK19X4qAXK0PTyVDDBipCZDhQqiXbzvwQu-5Gg-bfnvxI_wJ_0Nz4_fcNQsQLG-EytvztlUztJEbYTHPcbGhwexn6P4a1NLB8l6MyHYqpEYcHOgCHw6Gd4gmsviM4ceX0xr8A92tL8bqAsv2mhku24w4X8EHQxxLobPo6ch2OypmeLe1_0pMKLuHvOnQerRZm6_x7RzJE0aPKLauEDwHtxOs3LUtBBpZL2bmbjSZmNM9jxaEs7iATclZ8kzd8fAeMlcu3Pif6XAr7zKvxLY3qyP1U-WEVQS4rHwqHYTEEQhTR3-37UMVNLYd7DRSbOBrUcgXD4rVuxoOuFq-WjWddMCKrNO7tgdtZBGamlAFdRQzGrZYjqBUaIvVbRt23O_QBSl26H-V-4wPSAw5zZqpBXEkVCfxXCjHbu0rFvr9gaWDY08yh--7p6ogaBa1_wmD0xCG4OKXqKAPmvWemZLLkUTW2BrUm8n6fDytTVulV2ru5S3O3ToBgtCtWAVxhp2-3AwkNxZU-UM57zHMSgtMhkPTDnphXhipAIP4mamedIKaP8-_ULxDktQidP0BeTcKXSOR-w893NDtO8WeERdX2uWfFjdeC4soDy9qC6SAtmLvHZVKDZoRyauDLx6OOmAAxvL8m9Hnai3XaZ8YXwj4JbcYN7iK6XgDViuFNVIbCqqGMCmoazCmpPQgLYke_QRlIvAmYC0214uZ9bXSfgH0O5nffhCGIn5yr-KHpMP_sLGN7duo7YPPH1_-R1kTKgCfYkFiWYVud56fwTO0WF82yl4N0WZ4I4nlNA2ZPF6j1Z5TJ-Zlzo-VeLuVupO87h4yGxTUDwQd-nymf1CAz1tk3NQRSR9ToQWtDtSuL68u8feOyRE86OsQ9akUwTidKmD3Iulucq5uX68zK2qpnRo3b1gRUOH1X1d-Ga9WJiAY3kKHc0QhbJCyPka_

CU21: Rechazar Postulacion especificacion
El Proceso Principal Caso de Uso Base CU21: Rechazar postulación: Es la funcionalidad central dentro del sistema SYS PASANTIAS — POSTULACIONES. El actor Empresa interactúa directamente con ella declina expediente de postulante para actualizar el estatus de la solicitud a Rechazada en la Base de Datos de Pasantes.

Las Relaciones Obligatorias include: El caso de uso principal depende obligatoriamente de un subproceso del sistema para completarse con éxito:

Despachar alerta automática con el motivo de descarte: El sistema envía obligatoriamente un mensaje informando las razones de la declinación.

El Flujo Excepcional o Alternativo extend: No se especifican flujos opcionales o condicionales de extensión en el diagrama provisto.

En resumen: El caso de uso permite a la Empresa declinar el expediente de una postulación activa, obligando al sistema a actualizar su estado a Rechazada y a despachar una alerta automática con el motivo del descarte, cerrando la solicitud como no seleccionada.
TPJFQjj04CRl1h_3u1m21XjBiHF761FPbY4G4bCbXqAWJ5PJUucqw-wkaYQba4jllRN7GcclFVROM_8cUO8-GdSL9NKSMJfeDN--_UcRHNlQe39PcbGh-foB1IfCGSynbfTSpC2eZ9OpIcOYPb89Kk1rbZF8Z5IHkKe8y9AqJ9_rdI4xdnNDYLImCGdSNQqy4oTcKCoimeTg1UmrVEeQ5Lt-f3rfDpR2JjWDkqMHL36fei0VROMTrdBYUCxPkI2jmNy8JwGm9TKk7F5h0g-z5CY_vqmcSRNoyJbifecXNe_gxtPRmzt6HcSSZ4E_1DKRjYSxVZcgr-oyW9tarogiNmxhOgLW_Rw-qeRIDtPUN8h1m89uEzrjQweN34UxenUa9HsjSDllU2k49NMFo2lMvKTbhN7ZhKwxrR8ptju9_JBZWfRDhvbncN7bKrvZN8xw05WBquKYZJL03NRz51-wkSS4OpHIkyKKDGf3EgySZg7VZxYp0WS39_V_NDUYrn5CWoWuFDuF8hY_-GhJe-Zuv20OxHyTXb7jqPN7qrKRdJHyxrIy8ZR7QrImaDfa2J9-zrlasurEV6-bPqnwWRPU0IQa309cHgPtFmnd24oAKq49fDBm2-deOzBC_WCebmkOyU35A0jVh0dGQ0poFQ47Os895mZqVa4n9-k0aoi8xLkraXSscuC7sHxS_kA29LbCjt-Af9EpZlLSHOO9lxPozfTaijnOBHFEkCbYGDWiF8Xnqx48QRTJV3Ot8Dy-kV3t-vVFKAzFhULIn3otgLUlkzJzpKzBV4OMrmw7AyWi-hATxbpo2sowuhpXsoSdPIjAjGvMkjzb55jxIIbqJvbA418q9SIODT46hJA961nvjR9dbrdw3m00

CU22: Generar Reportes especificacion
El Proceso Principal Caso de Uso Base CU22: Generar reportes: Es la funcionalidad central dentro del sistema SYS PASANTIAS — REPORTES. Los actores Director quien Configura filtros estratégicos y Administrador quien Solicita métricas del ciclo interactúan directamente con ella para extraer analíticas agregadas desde la Base de Datos de Pasantes.

Las Relaciones Obligatorias include: El caso de uso principal depende obligatoriamente de un subproceso del sistema para completarse con éxito:

Compilar métricas y estructurar documento analítico PDF/Excel: El sistema procesa de forma obligatoria los datos agregados y les da un formato descargable estructurado.

El Flujo Excepcional o Alternativo extend: No se especifican flujos opcionales o condicionales de extensión en el diagrama provisto.

En resumen: El caso de uso permite al Director y al Administrador, siempre que cuenten con acceso al módulo de analítica, generar informes del ciclo de pasantías, obligando al sistema a compilar las métricas y estructurar un archivo en formato PDF o Excel para obtener el documento definitivo solicitado.
TLJDQjj04BuR_0w3SsaDTYt5JXnZJ6HRBhsq9aeEXK1PhpRAajLks5sHfAMGIs-zjST2eRTGUignj_XDyWHzXCxAyayIPNMHvkURRxwPrRwnHDii5TMAEUFod6YIWZabiRhWCW6hCxRfqIgJCLLQCWrUPzD3g5KwibU20RbWHgKFycQ4dYL5ib0QjYQ1UwgL1-2CMY8JHFXKhG2UuIfhL6Jva_QatTWAEs4tx1P1IiTC5m7-Q3lij3OTXwUSdabc3FWByqH9MnBjp17_oC1hRnZoVcPAnDNAvuTaCyCeCSzJzVUwhU5UOwip3iQXNqBL6xOdktuvLQ_PUK9saf_7PFroiivMIgpVDrV6ilG3peihEHWW4M-tkuEYUi5mj3TwmhGaenNk-1tl4SEIk2NbHzBbg_AiSEFjJhlLmXdlx8P-cN112_tFpBXCkF8fFoDSJdL1i3RcRYELhW4nW1yhHn2dN79ZDLwJXJUthFn3jnWnWp6nohYNAJ54McRosE4O-ls8Ewt8OE3ghHU_5hsFO1f4mTl3Dq44zzVVuI2SlZiu3AFQKh7bvjL6HmtVFvQl6Tv6el7wd2kzB38wMcgt3bVfEHSOcCvlhEPeX2jWs4L6ROO0np9MD4kPj0g896B-ntAguCLqF7aLNb8cNYvQfTQ39yCkb4ELeD4OvEMX1oCbJtY2u732XTKeXgj7xFmcGMXJhUIwRMP4Id3ABTaW6JC1b5EXgfKygDaSB4ZquEutbrHaCRlxMpWT50hSW_0I2x5r8mX44iqI4XFZc4fb6MYUd5fG9okv_ltyzXNgzIbEHCaOcSnlPQzUTwxxwryG2fGp8vehP3LZO9tqkCyKVtX019A-ZJFXd1k5couxH_ZnnM4hOql18mPgPZb20dQydeNhlvWjc4AUM24gap6uDggLVNpDqly0

CU23: Consultar Historial especificacion
El Proceso Principal Caso de Uso Base CU23: Consultar historial: Es la funcionalidad central dentro del sistema SYS PASANTIAS — REPORTES. Los actores Director Consulta auditorías pasadas y Administrador Audita flujos históricos concluidos interactúan con ella para consultar las tablas de histórico archivado en la Base de Datos de Pasantes.

Las Relaciones Obligatorias include: El caso de uso principal depende obligatoriamente de un subproceso del sistema para completarse con éxito:

Estructurar línea de tiempo de procesos académicos previos: El sistema organiza y muestra cronológicamente las acciones y flujos pasados del expediente.

El Flujo Excepcional o Alternativo extend: No se especifican flujos opcionales o condicionales de extensión en el diagrama provisto.

En resumen: El caso de uso permite al Director y al Administrador auditar registros pasados bajo la condición de tener el acceso concedido al sistema, obligando a la plataforma a estructurar una línea de tiempo con los procesos académicos previos para visualizar la información histórica requerida.
TPI_Rjim4CPt0tw7WxCPi679Tk84XX5Pbe4khH4bGu401ICoDXk9T4agGLeKoDAjMpiMAD2jA39bx1Q_IPwWZz0Z_JUEB2yqxxlZJzyTTQmDKIRFqd99Nt4n9Ofae2U4oXiknc1KpZOZIkQ29b89fi1hRqP8OgIApMtAWDmmBRDdUHSakHelabEfO6yOs5-vzAmuImmHOwpmgLm2VFghh72HvGzRmrPjBsf7dQYp44b5cLe8_B0PjHkRWTC9Jwu4qnhy-VPG2bEWjjin_yZ0QsrikFUva2ajbpu_XyqrIuZUZUeVTXhzmzfUUn0C8hy0rUktXWT-CQfNRx-07Rfd6zOlXhLxXM3ThhxLXcNli5zSYbuFGRo3pZwQwWNzy31yGLgGqOZs_RQtHLYWMo9lMUT6PQTnWsQxrMXWZ_SF8h_8kA21yHqzBZAkkCixZ7EeSy3AWDk9bAe2H0F-MGK2cd71jL5uJUPHjxEAz-rWK0O3OgIsYn7HH1YcdRO_W6utvjOhqklPyzQ3NudVnZ0Auk3rwQiWXgUxxt0IZTwSd4PnPUdOSl8guLdDRvwBK0gTftYDOO95fU8aTUU4PtvpAoD2vZmnkK9nEhiNZ5WwmrasbRWw5rCb4xoy6dj4wEntnXDSJnMxvd8E7oJ6WnUjNlY67a6jrdCdmn4imO3ab2FOx1uBJD4AIdIvv2pRb0TMHU0opT_ZeVPTPW_A0IHI96a-kwSIyvowNk_DKOxWyG-tKSeU_ow2jYQQl05Wo4LAN2VMPO6ePCAliOKMNKZ3GF7nn82yN5dtx-Uthr2jZh11Kb2UyDc3EAfMRUZfxXSIMBE0fA3dxNIaZ78gwrRZT3--s0fIcy8ICOCiPtQK82N0nQLK6N4YIxis3kGQdU2NyaFE5AS4Zs62WgKlbuvncMV_0G00

CU24: Asignar Supervisor especificacion
El Proceso Principal Caso de Uso Base CU24: Asignar supervisor: Es la funcionalidad central dentro del sistema SYS PASANTIAS — SEGUIMIENTO. El actor Director interactúa directamente con ella Vincula docente con alumno activo para asociar los registros de supervisión académica en la Base de Datos de Pasantes.

Las Relaciones Obligatorias include: El caso de uso principal depende obligatoriamente de un subproceso del sistema para completarse con éxito:

Desplegar docentes habilitados y enviar alertas de tutoría: El sistema filtra forzosamente la lista del personal apto y despacha los avisos correspondientes al docente seleccionado.

El Flujo Excepcional o Alternativo extend: No se especifican flujos opcionales o condicionales de extensión en el diagrama provisto.

En resumen: El caso de uso permite al Director enlazar a un docente con un alumno activo que cuente con una pasantía debidamente aprobada e iniciada, obligando al sistema a desplegar el listado de docentes habilitados y enviar las alertas de tutoría para establecer formalmente el monitoreo del estudiante.
ZLJ1Qjj04BqR_0-3SpFOM8gKECQOo9PSScWQK58e1CfwjPMNIBjcTvMGba8klVNM7Wk5tahfgSVUaZ_95_GJEYlBgUF8KEcosfbvy-QzNHrgGvGfygpPq1TSB8WYEUWvIUGL5oaOLR3rY9A5IAXKWYbm_FK8eKQgs5nd3CWLqp9_L3SZz2AjYZEfO6SQsBVPU0JEg24YHOHtpGRWCtwecbHLxjIRUfsTo8_wKRzAaYfXgafm9xkHtriFdCuvlH1CQt2NsrCfJ4sstOxvMmQEjxPHpZEJMT9il7zCjj2C4hsTgdlGxuqFEZj-68IHMqFL6NlJVRUUgjFrdv2TbiycMRUUhDsh9JOSwcjjMFuQ_U9IZ4P8nDdlxw6eJZ2U74oUCAsfw4LxhkziCAp9Mr7UaAuyAbk52tTzhzT3Z_Vs8xTEkA27yIqUrmbNx_8MuKggIuAjaDiJALKBY0RyU0YChV49Wv0OgUtYX6WY3DDbvZY4uJ3cLWio6bcyVmUx5R-AuII8W-FJeo26-vlF44VFpewU7qN7fozQAr5MXwirEUkutha8D4y5KQ2B1LENN5US9cUkjr4GCht8M8gvYQJCSe8vcV6C6xpI-bnS0nEN7CCaOygGahqfSAgxdwJ43AXnu8cNbJ0e0dGwex8n3E0b5xJ8oAeLK2aGjyY5j1xpIzbib9dTxcY9Eu3R7rYJ5Gcx_Lq5BHvADe10Iye9_WLIr4ujXLqDpEz-8JGboTttd5DYkGY97HLFvmRacmSf_dpzz17QxHEKN8g4KriuQBTjwFxc6qGPC6sAX5kxiC4CfsVsPrO80elIHHG2o4B96Ka8CE02GN3PjH0bp9SFje7KvZywq0A58QKmXLYp3vMsZYOIx9N00EHISBI1IMp4H09sl6RZ49T5_XS0

CU25: Registrar Seguimiento especificacion
El Proceso Principal Caso de Uso Base CU25: Registrar seguimiento: Es la funcionalidad central dentro del sistema SYS PASANTIAS — SEGUIMIENTO. El actor Supervisor interactúa directamente con ella Registra incidencias o visitas de campo con la finalidad de almacenar la bitácora en la ficha del alumno dentro de la Base de Datos de Pasantes.

Las Relaciones Obligatorias include: El caso de uso principal depende obligatoriamente de un subproceso del sistema para completarse con éxito:

Habilitar formulario de bitácoras y control de horas acumuladas: El sistema proporciona de forma obligatoria los campos de texto e interactivos para asentar las visitas de campo y actualizar las horas de práctica desarrolladas.

El Flujo Excepcional o Alternativo extend: No se especifican flujos opcionales o condicionales de extensión en el diagrama provisto.

En resumen: El caso de uso permite al Supervisor registrar los pormenores del avance de un estudiante que tenga asignado, obligando al sistema a habilitar el formulario de bitácoras y el control de horas acumuladas, logrando así añadir una nueva bitácora de seguimiento al expediente de la pasantía.
TLJDQjj04BuR_0w3SpFOM8gLECQOoBRSvj0qLCcX42XZQMClaNRDxYffMWgvzDPRUooKzbfwA3ts5hz9dg2Fq5dv9uuZIo2a-Vdccsz6UwWDAfEbIRcaBxcOei8Kz0HZUSt568pAsBf7oKp4aLI2AN2yTGz6HghGt2GCy9ffcJxA6s5qELua9rB1pj2tTxdq29n51iMO4DwNIq1NRvNLNsIvm-QmMTi9lA0Lj1P1KiLCBGBS_cxWDTOTfnCUNGgcDRXpyr0AKn1jpI5_ny1fhXdoVaOoYSkb3u_9Pff5gBTJTGzQZTv1RSSR-8F0BQ3gz9h3VRUOgbFtdf0TvjScMRUOhBKL4kjqz8qsB7r3y-9ITBj4nDblxP6eZj_h7_IVC2t8Q0HxhkTiC2o8MrBUa2vVbQt23NQzPgD1CzxR3zmYuVm6-RVCk4YuuYbl4IwdEYTO2RCfKrTSIrK1r42VArVFZZvcC40ZjNqvGOt2C9r7zWRGwOJSge7ThaLyMErA-3g44p_qZq-F_13kRxz063mxEtfn51oVlgmiPLckLwL_LdEzS_6AZGbFeGBDnXbFEHD6viNwPwwtaVCSHppXz6F3XLHfbg3Yqf8SSJFxJdylwdDn0n6rhcHY7HDhexbaDZZ6UHT-P1nuCjM5H2G6r6hTl3gqOKaFk8XupEX10198FAAH2nHXEfNbKXvVhtVdw6su-qaPIHQpkxyBfqKb0TlW9ob6JE03RM024eGB7asGC1F094k5j7o4D0mK7qyCo8kL9l--VVu4rUe9oIz5p2C--oFQrQfrtT_-W201lPen0OuO66QFDjHyBEWCf0AB6dMRa-Tz_MWHfJQ5a24TVxFVI0rdn5nax6gTFvdNncVHsTifY-rNlaxKt3HVfDalf8fCn60RAvSEwJLB_mC0

CU26: Evaluar Desempeño especificacion
El Proceso Principal Caso de Uso Base CU26: Evaluar desempeño: Es la funcionalidad central dentro del sistema SYS PASANTIAS — SEGUIMIENTO. Los actores Empresa Evalúa competencias corporativas y Supervisor Asigna notas de informe final intervienen en ella de manera directa para consolidar las calificaciones de la pasantía en la Base de Datos de Pasantes.

Las Relaciones Obligatorias include: El caso de uso principal depende obligatoriamente de un subproceso del sistema para completarse con éxito:

Desplegar matriz de rúbricas y promediar calificación ponderada: El sistema muestra forzosamente la matriz evaluativa e instrumentaliza el cálculo aritmético con base en los pesos asignados.

El Flujo Excepcional o Alternativo extend: No se especifican flujos opcionales o condicionales de extensión en el diagrama provisto.

En resumen: El caso de uso permite a la Empresa y al Supervisor asentar las notas de la fase de culminación de un alumno cuya pasantía esté en etapa final o concluida, obligando al sistema a desplegar la matriz de rúbricas y promediar de forma ponderada su calificación formal por las actividades efectuadas.
TPJFQnf15CVlWl_3mzm4nTseCIAILTSIQDF09eT2e3ntHpDaTsOxCvkGb48klVNM7Wk5NaiFfRVq5l-J_0Nz4_fcDTQOTRsix-Tdlk_j76Y3ocH9N2xf2ovIL9Y0FiT8Nd4n0wCojkvHCXDHA9LW2fpMkWT38rLWhcC6UCMqJ9xaJJ2yc2sJOwbWP-pPNxdqf3WB3OePLNXVBW4zWrNMS9dbZflZPct7R_aTlxCCaYfYQXdW3dVzLcFTSNBEmml1j0PtOHvBOGgYhJdWDmoSvfeXFyz4nb6vzE4fRAPPY7exghlVQGpsQpkjaJVotG9KPz0Sxxd5g4wzzGnsd3-Ri6unhBKLWlLw-beRbhobUN4f-dq2SVOwRHBLyGR3_U4pqeACXjzsMyu6OK7S8_A6TFcgR1LkjDjgDXequ_QUxnO9vpN8lsN6HS8LJtcBS3dg0h3Y9wbY6Yk06kXzPG-obAbBhgNANVHtvHhObOWOZD18RL-EKQCmJEUHWn7qUW6tAc6_RplzN_bAy2Q0Oo_mZauElG0URhz0uByuFNnrw1-TlAuyolMuTfNXQSrjdmd_4kCC5RNIB4dP_9VCEmrFtVP6meZfD6OpYatGA7vZwTJyRg8u-S_4DQIAFjg8Kq28CP-IEUJptm9IAKXZZ1P2UA5nuDcibyAHIb2hzVFsq0KBDxz322MX6IP2JWNezaYbGiClKPTB9DvwXgVvJ208QJ2NZukfL0c3AHT8LrGULQ_t5nHTkF_1HHXd4Rl_itJQMYHp5uPIQ1dp2DTE8sb7RDKO8StdCl-95flQaHPyTcv0JbVQ_Vts-HDKgySq8rA0vs9qgrNhUhZz3Y_NYb3H2GDcxr9W0dG6p62A2soGT6QBIJ1rcvrN-FhHrfRQ51RtOrijesdGyi2xZD4vM3xgI8AL1EE4MHT9IUsq_QRu9JMWFQ0UJ4HMGxg23-WrI_u1

CU27: Emitir Constancia especificacion
El Proceso Principal Caso de Uso Base CU27: Emitir constancia: Es la funcionalidad central dentro del sistema SYS PASANTIAS — CIERRE. Los actores Director Autoriza egreso de pasantía y Administrador Modula expedientes aptos interactúan de forma directa para liberar la constancia oficial descargable desde la Base de Datos de Pasantes.

Las Relaciones Obligatorias include: El caso de uso principal depende obligatoriamente de un subproceso del sistema para completarse con éxito:

Validar requerimientos mínimos e incrustar firma QR digital: El sistema efectúa de manera forzosa la revisión de condiciones de cierre y estampa el código QR con valor de firma institucional.

El Flujo Excepcional o Alternativo extend: No se especifican flujos opcionales o condicionales de extensión en el diagrama provisto.

En resumen: El caso de uso permite al Director y al Administrador emitir el documento acreditativo para estudiantes que hayan cumplido las horas requeridas y aprobado sus evaluaciones, obligando al sistema a validar los requerimientos mínimos e incrustar la firma QR para poner a disposición la constancia de pasantía oficial.
TLH1Qnf15BuB_eU7kGcAkz5eH2IhhX18IngJGY5GdZiJ7R8xOsTccoQba4jllRN7Gg7NabEFlIN_9B-WFw5lLcFLh2le-jxtvllcUs_cm5ZKDatYOi5S2Zb3ZGcOAJ9r9UG4h4xvQaQhLB98QSarU8tL34PMwP6zZZdW5JSgMQiROtGvMHJ7IiFEC72VOc5jSHvPb1DQuMEn0FJqbbNzHPK_h0_hbPsm4RR2rWAaDEDw0V3xks6ZjfeudOheKd9Zm9-7XqhQ7BGBZyGD1w--4iZsCrOnAnO-hOjD3O_GR9VgxxTglVtAJcCG348_HwhNgm-RVhvKhzfu9dQOFPjY_NonBfOhhDCnryRov2trIoZPxP8GhzdQ8rEzeDVVxpzJcbDH2_VyXhUXC0Vt97d3kcnKjXets6tKQpNgyLupzFEC2sgKtzBZFEFokxp5k4pgN61f8Dn4Abq2D41_bec09K8AOpKTatasYoppFJSOZCC0hJBkvHWDIijDXkqDeDCP2USLThkEx__WbqPlHd0SZ8ANfuV121vllq7_C3mv2KjFVZtDNQb_Ll6Rvp9CX1KQ8YNf9Cj8OCRHF_ER6_ZN60k6caxPkvHhaGWkdRhauKwAH9bpoK78IAVkGe0BeHE4LoV0n4HOZEURZAm7pzgyy8pyWKgbcp536uAKd10t27oYwJPm9imo4nxki5Z8x5g5lr0iZGdyOSQP4yODu8pa5GiPe5hjpjdRSF-BLCOfu_T_5act37dQXYCnvXfNh01r8UWd9dOJePxWEEPEgrIMWnQJgIN4qgk_Fxv-WNBvcBgX9AF2Xz-oNIwxrEFjJmXZuCQcJBXEqefZ3bCaGeZIP4RMAaSCCVaqLPg-5pupUhq6ozsDYJEjnkWY3iRVOvnYH2PoKtKi6TFtpqw3CZPNnD7QzbPD9N70tImm9BvPIbeH22BCJ9dvEaJ29GEt-sBXW5xJv1y0

CU28: Cerrar Proceso especificacion
El Proceso Principal Caso de Uso Base CU28: Cerrar proceso: Es la funcionalidad central dentro del sistema SYS PASANTIAS — CIERRE. El actor Director interactúa directamente con ella Concluye oficialmente el ciclo para cambiar el estatus final del expediente a Archivado / Concluido en la Base de Datos de Pasantes.

Las Relaciones Obligatorias include: El caso de uso principal depende obligatoriamente de un subproceso del sistema para completarse con éxito:

Verificar checklist completo y archivar expediente físico/digital: El sistema revisa de forma mandatoria que no falte ningún elemento formal en el legajo y ejecuta el resguardo en el repositorio correspondiente.

El Flujo Excepcional o Alternativo extend: No se especifican flujos opcionales o condicionales de extensión en el diagrama provisto.

En resumen: El caso de uso permite al Director dar por finalizado oficialmente el ciclo de prácticas de un alumno, requiriendo como condición previa que la constancia fuera emitida y todos los documentos archivados; esto obliga al sistema a verificar el checklist de control completo para trasladar el expediente al archivo histórico y liberar al alumno del proceso activo.
TPH1Qnf15CVlWj_XOGu1gSRTQ6A2IDPrXK0f4fD28L36sOaEpix8p6nJMmgvzDPRUomKUYqzvTXRyato2VeH-cPTKsFMzJBEU-__VlD_itjYBD4sJKIvP6PSpeac2PWfYTKrbnEmEcNh4QrI6LEb9TFWjTOZX5gbHtOX691hPbJof6vCw6oI5mkbOMSGk5-vz4ISKKla11K-bak0J--nAioh_45pqApjHAse7RNp9ALZflC4FzoFMetrmFcKqvbane2_t1ueQGkotVQ8Vs3WDTSsilECbOZBfKzFOLF3A37RKVsZTgDtLDjfzOD-v1UWUhtcuD0lHlNghMUmW-pPXFMBOTrU8LYdOnR6ikGjpeihsUqYY7VOFa1JlQ0N7eNFI0ig6j61t_8s20loLiWRrcLNPQjn_VrMiz706HySHdwHSK43urjcN6HSyPIt69UXBW4hVUvkfD8L80RmpsEWvmOVC-WJgunR38aXqZAJPVRwqEcCkFE2TBjEx__5hepUZ60OZ89NvwV121vkla5u6fsTHPML7wjxLGalQdxxKePCQw9XhXN5jofh45xuxOtarqppAqunaKuPdGdi3bGbSy6ikfGB89fE-JiCi_Tp5dE6i71r_zjmglPYFk6MY4mweDQ3PvFCRK4Be5RhPltX648bgKWN31HsvaGacIeJG3aLgbpAqkhrxbBq6Ev-SLSGixi_UT29eLieHP8n9y3mOsHJ0rTS4W44TeCbTgnWBs_7OxNhMAJ2NffFfXRRFphozyVNBr2j3j5m9MEakh-LnzMg2ptS_8IN14sHs4GYByvjZ74m-2bZ2RSy9h00gs8SgN1ZLJHrHy8bMM6OkfFAvBv_TesKiOMT8h7kz1ol1xWJPJeAfZYU-rkDvYE40BEyAoz0y37JHE9nNR984xbCo8VlNXmiHmOcOt0Eb4idk4oJVm00

Quiero tomarme un momento, con total calma y sinceridad, para expresar el profundo agradecimiento que siento hacia ti. A veces el día a día nos lleva tan de prisa que dejamos por sentado el valor de las personas que nos rodean, pero hoy no quiero que sea uno de esos días. No quiero que el tiempo pase sin que sepas lo mucho que significas para mí y lo mucho que valoro tu presencia, tu apoyo y tu entrega.
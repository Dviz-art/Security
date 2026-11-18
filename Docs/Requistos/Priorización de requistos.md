 Priorización de requisitos

## Método MoSCoW 

| Categoría | Significado |
|---|---|
| **Must** (debe) | Sin este requisito el sistema no cumple su objetivo. Entra al MVP. |
| **Should** (debería) | Aporta mucho valor, pero el sistema funciona sin él. Entra si alcanza el tiempo. |
| **Could** (podría) | Es deseable y de bajo costo. Se incluye solo si sobra tiempo. |
| **Won't** (no por ahora) | Queda fuera de esta versión y se documenta como trabajo futuro. |

Cada requisito se evalúa con dos criterios:

- **Importancia:** qué tanto contribuye al objetivo del proyecto, avisar a contactos de confianza de forma rápida y discreta.
- **Factibilidad:** qué tan realizable es para una persona trabajando sola, con servicios existentes para cuentas y notificaciones.

## Requisitos funcionales

| ID | Requisito | Importancia | Factibilidad | MoSCoW | Justificación |
|---|---|---|---|---|---|
| RF-01 | Registro de cuenta | Alta | Alta | **Must** | Sin cuenta no se puede vincular a los usuarios; existen servicios que lo resuelven. |
| RF-02 | Inicio y cierre de sesión | Alta | Alta | **Must** | El widget y los avisos dependen de una sesión abierta. |
| RF-03 | Permisos del dispositivo | Alta | Alta | **Must** | Sin permisos de ubicación y notificaciones las funciones principales no operan. |
| RF-04 | Invitación de contactos | Alta | Media | **Must** | Es la única forma de construir la red de apoyo; requiere configurar los enlaces que abren la app. |
| RF-05 | Respuesta a la invitación | Alta | Media | **Must** | Garantiza el consentimiento de quien recibirá la ubicación. |
| RF-06 | Gestión de contactos | Alta | Alta | **Must** | El usuario debe poder retirar a un contacto para proteger su privacidad. |
| RF-07 | Mensaje de emergencia | Media | Alta | **Should** | Mejora la claridad del aviso, pero existe un mensaje predeterminado. |
| RF-08 | Inicio del aviso | Alta | Media | **Must** | Es el propósito del sistema; el widget en iOS tiene límites de interactividad. |
| RF-09 | Cuenta regresiva | Alta | Alta | **Must** | Evita avisos accidentales, una de las ideas centrales del rediseño. |
| RF-10 | Envío con ubicación | Alta | Media | **Must** | Es la función principal; requiere servidor, notificaciones y ubicación. |
| RF-11 | Confirmación discreta | Alta | Alta | **Must** | La discreción es el diferenciador del proyecto y es sencilla de implementar. |
| RF-12 | Notificación al contacto | Alta | Media | **Must** | El aviso solo sirve si el contacto lo ve; en iOS depende de las reglas del sistema. |
| RF-13 | Detalle del aviso | Alta | Alta | **Must** | Sin el mensaje, la hora y el mapa, la notificación no permite actuar. |
| RF-14 | Botón de emergencias | Media | Alta | **Could** | Es la función más sencilla y no afecta a las demás, por lo que se puede añadir al final. |

## Requisitos no funcionales

| ID | Requisito | Importancia | Factibilidad | MoSCoW | Justificación |
|---|---|---|---|---|---|
| RNF-01 | Tiempo de envío | Alta | Alta | **Must** | Cada segundo cuenta en una situación de riesgo. |
| RNF-02 | Tiempo de notificación | Alta | Media | **Should** | Depende del sistema operativo, por lo que es una meta y no una garantía. |
| RNF-03 | Rapidez de acceso | Alta | Media | **Must** | Es la promesa central de la propuesta. |
| RNF-04 | Tamaño de botones | Media | Alta | **Should** | Reduce errores de toque, pero se puede ajustar después de la primera versión. |
| RNF-05 | Resultado del envío | Alta | Alta | **Must** | El usuario no debe creer que pidió ayuda cuando el aviso falló. |
| RNF-06 | Uso de la ubicación | Alta | Alta | **Must** | Protege la privacidad y es fácil de cumplir al no haber rastreo. |
| RNF-07 | Comunicación segura | Alta | Alta | **Must** | Los servicios actuales ya cifran las comunicaciones por defecto. |
| RNF-08 | Compatibilidad de plataformas | Media | Media | **Should** | Compilar para iOS exige una computadora Mac; si el tiempo no alcanza, se prioriza Android. |

## Resumen

| Categoría | Funcionales | No funcionales |
|---|---|---|
| **Must** | 12 | 5 |
| **Should** | 1 | 3 |
| **Could** | 1 | 0 |
| **Total** | 14 | 8 |

La mayoría de los requisitos son Must porque la lista ya se redujo al mínimo necesario. La priorización real está en lo que se dejó fuera.

## Fuera del MVP (Won't)

| Función | Motivo |
|---|---|
| Check-in de seguridad | Ya viene integrado en iPhone y Android, y requiere servidor de temporización y ubicación en segundo plano. |
| Aviso por SMS | En iOS una app no puede enviarlo por sí sola, lo que rompe el aviso rápido y discreto. |
| Funciones sin conexión | La aplicación está definida para funcionar solo con internet. |
| WhatsApp como canal de avisos | Su API oficial requiere un número de empresa, plantillas aprobadas por Meta y un costo por mensaje. |
| Mensajes adicionales | Mantener un solo mensaje conserva el aviso en uno o dos toques. |
| Ubicación en tiempo real | Agrega rastreo continuo y mayor complejidad de privacidad. |
| Reloj inteligente | Requiere desarrollo aparte para Wear OS y watchOS. |
| Ficha médica | No es parte del objetivo principal. |
| Inicio de sesión con cuentas externas | El registro con correo y contraseña ya cubre la necesidad. |
| Eliminación de la cuenta | Se requiere antes de publicar en la App Store, pero no para la primera versión académica. |

## Orden de construcción sugerido

1. **Cuenta:** RF-01, RF-02, RF-03.
2. **Contactos:** RF-04, RF-05, RF-06.
3. **Aviso:** RF-08, RF-09, RF-10, RF-11.
4. **Recepción:** RF-12, RF-13.
5. **Complementos:** RF-07 y RF-14.

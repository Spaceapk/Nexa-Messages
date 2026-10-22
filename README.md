# Nexa Messages

Aplicación nativa Android en Kotlin y Jetpack Compose. Paquete `org.nexlibre.nexamessages`. Versión de prueba **0.1.1-alpha**, Android 8 o posterior.

## Corrección dual SIM

- Elige SIM 1 o SIM 2 desde ajustes, al redactar y dentro de cada conversación.
- La elección del chat prevalece sobre la general y se conserva al cerrar la aplicación.
- Las respuestas desde notificaciones también respetan esa elección.
- El selector pide permiso Teléfono para consultar las SIM activas. No consulta números ni identificadores privados de las tarjetas.
- Si la SIM elegida no está disponible, bloquea el envío sin utilizar otra tarjeta silenciosamente.

Comprobación local: compilación correcta, 13 pruebas aprobadas, lint sin errores, firma debug válida y compatible con la primera APK entregada en ChatGPT. Los envíos con dos SIM físicas requieren comprobación en el teléfono.

## Código fuente y compilación

El proyecto completo y organizado se conserva en **nexa-source.zip**. Contiene `app/`, Gradle, fuentes, pruebas e informes. Se puede extraer y abrir en Android Studio. Incluye un respaldo del historial local de recuperación.

El workflow `.github/workflows/android.yml` extrae ese archivo únicamente en el directorio temporal de GitHub Actions, ejecuta las pruebas y lint, compila la APK y publica los artefactos. Solo tiene permiso de lectura del repositorio; no crea commits ni hace push. También puede compilar archivos nativos colocados directamente en el repositorio si posteriormente se retira el ZIP.

Para futuras actualizaciones se debe modificar la base existente y actualizar el código conservando el historial. No reconstruir desde cero ni cambiar el identificador Android.

Las APK generadas en distintos entornos pueden tener distintas firmas debug. Para actualizar la primera APK entregada en ChatGPT, usar la nueva APK entregada allí, que conserva su certificado. La firma estable permanente todavía no se ha configurado.

## Alcance

Primera entrega centrada en SMS reales por operadora, contactos, conversaciones y notificaciones. Dos estilos: Google Material 3 e iOS clásico sin Liquid Glass, con claro, oscuro negro puro y seguir sistema.

MMS, mensajería por Internet, adjuntos, E2EE y llamadas siguen pendientes. No usar esta alpha como aplicación habitual si se necesitan MMS. El plan y las pruebas manuales se incluyen dentro del proyecto.

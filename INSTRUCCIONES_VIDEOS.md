# Instrucciones para Configurar Videos de Referencia

## Problema
Los videos de gestos están en `app/src/main/GESTOS/` pero la aplicación necesita acceder a ellos en tiempo de ejecución.

## Solución Recomendada: Copiar Videos a Assets

### Opción 1: Copiar manualmente (Más simple)

1. **Crear estructura en assets:**
   ```
   app/src/main/assets/GESTOS/
   ├── BASICO/
   │   ├── ABECEDARIO/
   │   ├── Numero/
   │   ├── MESES/
   │   ├── Frases esenciales/
   │   └── Necesidades basicas/
   ├── SOCIAL/
   │   ├── Saludos y despedidas/
   │   ├── Comunicacion basica/
   │   ├── Colores/
   │   ├── Emociones y sentimientos/
   │   ├── Familia y relaciones/
   │   ├── Actividades cotidianas/
   │   ├── Lugares y direcciones/
   │   └── Tiempo/
   └── ACADEMICO/
       ├── Material escolar/
       ├── Conceptos academicos/
       ├── Asignaturas/
       └── Acciones academicas/
   ```

2. **Copiar todos los archivos .mp4** desde `app/src/main/GESTOS/` a `app/src/main/assets/GESTOS/` manteniendo la misma estructura de carpetas.

3. **Actualizar VideoPathHelper** para buscar primero en assets.

### Opción 2: Usar almacenamiento externo (Recomendado para producción)

Los videos se copiarán automáticamente desde assets a almacenamiento interno la primera vez que se ejecute la app.

1. Copiar videos a `app/src/main/assets/GESTOS/` (como en Opción 1)
2. La app los copiará automáticamente a almacenamiento interno en el primer inicio
3. Los videos estarán disponibles offline

### Opción 3: Script de Build (Avanzado)

Crear un script Gradle que copie automáticamente los videos durante la compilación.

## Estructura de Nombres de Archivos

Los nombres de los archivos de video deben coincidir exactamente con los nombres de los gestos:

- **ABECEDARIO**: `A.mp4`, `B.mp4`, `CH.mp4`, `LL.mp4`, `RR.mp4`, `Ñ.mp4`, etc.
- **Números**: `1.mp4`, `2.mp4`, `11.mp4`, `20.mp4`, etc.
- **Meses**: `ENERO.mp4`, `FEBRERO.mp4`, etc. (en mayúsculas)
- **Otros**: El nombre del archivo debe coincidir exactamente con el nombre del gesto (sin extensión)

## Verificación

Para verificar que los videos están correctamente configurados:

1. Ejecuta la app
2. Navega a cualquier gesto
3. Deberías ver el video de referencia reproduciéndose automáticamente
4. Si ves "Video de referencia no encontrado", verifica:
   - Que los videos estén en la ubicación correcta
   - Que los nombres de archivo coincidan exactamente
   - Que la estructura de carpetas sea correcta

## Notas Importantes

- Los videos deben estar en formato MP4
- El tamaño total de los videos puede ser grande, considera comprimirlos
- Los videos se reproducen en loop automáticamente
- Si un video no se encuentra, se mostrará un mensaje informativo


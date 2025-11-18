# Repositorio de Lengua de Señas Ecuatoriana (LSE)

## Nota sobre recursos visuales

Esta aplicación necesita referencias visuales (imágenes o videos) para cada gesto de la lengua de señas ecuatoriana. Actualmente, la estructura está lista para almacenar y mostrar estas referencias, pero necesitas obtener o crear los recursos.

## Opciones para obtener recursos visuales:

### 1. **Repositorios y diccionarios online de LSE:**
   - Busca diccionarios oficiales o institucionales de lengua de señas ecuatoriana
   - Algunos pueden tener videos o imágenes disponibles bajo licencia educativa
   - Verifica los términos de uso antes de incluir los recursos

### 2. **Crear tus propios recursos:**
   - Grabar videos con intérpretes certificados de LSE
   - Tomar fotografías de alta calidad de cada gesto
   - Asegúrate de tener los derechos de uso

### 3. **Almacenamiento:**
   - **Local**: Puedes almacenar los recursos en `app/src/main/res/drawable/` o `app/src/main/res/raw/`
   - **Remoto**: Puedes subir los recursos a un servidor y almacenar las URLs en la base de datos
   - **Híbrido**: Descargar recursos remotos y almacenarlos localmente para uso offline

## Estructura actual implementada:

### Base de datos:
- La tabla `gestos` ahora incluye los campos:
  - `url_imagen`: URL o ruta local de la imagen del gesto
  - `url_video`: URL o ruta local del video del gesto
  - `descripcion`: Descripción textual del gesto (opcional)

### Actividades:
- **GestoReferenciaActivity**: Muestra la referencia visual (imagen o video) antes de practicar
- **PracticeActivity**: Permite practicar el gesto con la cámara

### Flujo:
1. Usuario selecciona un gesto de la lista
2. Se muestra la referencia visual (si está disponible)
3. Usuario puede practicar el gesto
4. La aplicación verifica si el gesto se realizó correctamente

## Cómo agregar referencias visuales:

### Opción 1: URLs remotas (recomendado para actualizaciones)
```kotlin
dbHelper.guardarGesto(
    nombre = "Hola",
    categoria = "Básico",
    dificultad = "baja",
    urlImagen = "https://tudominio.com/gestos/hola.jpg",
    urlVideo = "https://tudominio.com/gestos/hola.mp4",
    descripcion = "Saludo inicial con la mano extendida"
)
```

### Opción 2: Recursos locales
Para usar recursos locales (drawable o raw), puedes usar:
- `urlImagen = "android.resource://com.example.app/drawable/gesto_hola"`
- `urlVideo = "android.resource://com.example.app/raw/gesto_hola"`

## Próximos pasos:

1. **Buscar o crear repositorio de LSE**: Identificar fuentes confiables de referencias visuales
2. **Obtener permisos**: Asegurar que tienes los derechos para usar los recursos
3. **Implementar descarga**: Si usas URLs remotas, implementar un sistema de descarga y caché local
4. **Actualizar GestosInitializer**: Agregar las URLs o rutas de recursos a cada gesto cuando los tengas

## Recursos útiles:

- **Federación Nacional de Sordos del Ecuador (FENASEC)**: Puede tener recursos oficiales
- **Instituciones educativas**: Muchas universidades tienen programas de LSE
- **Bibliotecas digitales**: Buscar repositorios de accesibilidad





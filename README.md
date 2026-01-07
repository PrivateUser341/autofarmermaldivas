# AutoFarmer Maldivas

Este proyecto es un bot de automatización ("AutoFarmer") diseñado específicamente para servidores de FiveM (como Maldivas RP). Utiliza reconocimiento de imágenes para detectar minijuegos de teclas (`W`, `A`, `S`, `D`, `E`) y simular su pulsación automáticamente, además de mantener un ciclo de recolección pulsando la tecla `E`.

## Características

- **Detección Visual**: Escanea una región específica de la pantalla buscando las teclas del minijuego.
- **Escalado Automático**: Ajusta el tamaño de búsqueda de las imágenes basándose en tu resolución de pantalla (optimizado originalmente para 2560x1440, pero funcional en otras).
- **Sistema de Seguridad**: Validación de licencia online mediante HWID (MAC Address).
- **Interfaz Gráfica (GUI)**: Panel de control simple para Iniciar/Detener y configurar parámetros.
- **Configuración Persistente**: Los ajustes se guardan en el registro de Windows para mantenerse entre sesiones.
- **Fail-safe**: Si la detección visual falla, utiliza un algoritmo probabilístico basado en las teclas menos frecuentes para intentar acertar.

## Requisitos para ejecución de codigo fuente

- Sistema Operativo: Windows.
- Python 3.x instalado (Recomendado Python 3.12), no es necesario instalarlo si solo deseas ejecutar el .exe.

### Librerías Dependientes

Necesitas instalar las siguientes librerías de Python:

```bash
pip install keyboard pyautogui Pillow
```

*Nota: `tkinter` suele venir instalado por defecto con Python.*

## Instalación y Ejecución

1. Clona o descarga este repositorio.
2. Abre una terminal en la carpeta del proyecto.
3. Instala las dependencias mencionadas arriba.
4. Ejecuta el script principal:

   ```bash
   python farmer.py
   ```
   *(O ejecuta el `.exe` si dispones de la versión compilada)*

5. **Importante**: Es recomendable ejecutar la terminal o el programa como **Administrador** para garantizar que las pulsaciones de teclas se envíen correctamente a la ventana del juego.

## Compilación y Ofuscación (Seguridad)

Este proyecto incluye un sistema de protección de código fuente.

## Uso

1. **Autorización**: Al abrir el programa, verificará tu ID (MAC Address) contra una lista blanca en internet.
   - Si no estás autorizado, el programa te mostrará tu ID. Debes enviar este ID al administrador para que te añada.
2. **Interfaz Principal**:
   - **INICIAR**: Comienza el ciclo de farmeo.
   - **DETENER**: Pausa el bot.
   - **AJUSTES**: Abre la ventana de configuración.
   - **INSTRUCCIONES**: Abre el manual de uso en el navegador (GitHub).
3. **En el Juego**:
   - Sitúate en la zona de farmeo.
   - Pulsa "INICIAR" en el bot y vuelve rápidamente a la ventana del juego.
   - El bot pulsará `E` para iniciar la acción y reaccionará a las teclas que aparezcan.

## Configuración (Ajustes)

Desde el botón "AJUSTES" puedes modificar:

- **Tiempo Espera tras pulsación (s)**: Tiempo que espera el bot después de completar una acción (pulsar E) antes de volver a empezar. Por defecto: `9.0` segundos.
- **Confianza de detección (0.1 - 1.0)**: Nivel de precisión requerido para reconocer una imagen.
  - *Súbelo (ej. 0.95)* si el bot pulsa teclas al azar incorrectamente.
  - *Bájalo (ej. 0.80)* si el bot no detecta las teclas en pantalla.
- **Retraso acción (s)**: Tiempo que la tecla se mantiene pulsada virtualmente. Por defecto: `0.02`s.
- **Tecla de Pánico**: Tecla que cierra el programa inmediatamente al ser pulsada (Por defecto: F9).
- **Auto-Comer/Beber**: 
  - *Activar*: Habilita la pulsación automática de teclas `1` y `2` para comer y beber.
  - *Intervalo*: Minutos entre cada ciclo de comida/bebida.

## Recomendaciones para un mejor funcionamiento

1. **Resolución**: El bot intenta adaptarse a tu resolución, pero funciona mejor en resoluciones estándar (1920x1080, 2560x1440).
2. **Ventana del Juego**: Asegúrate de que el juego esté en modo **Ventana Sin Bordes** o **Pantalla Completa** y que sea la ventana activa.
3. **Interferencias**: Evita superposiciones (overlays) de Discord, Nvidia, etc., justo en la zona donde aparecen las teclas, ya que podrían bloquear la detección visual.
4. **Iluminación**: En algunos juegos, los cambios drásticos de iluminación (noche/día) pueden afectar la detección de imágenes. Si falla mucho de noche, prueba a ajustar la "Confianza".

## Disclaimer

El uso de bots o macros puede estar prohibido en ciertos servidores de juegos. Úsalo bajo tu propia responsabilidad. (Es indetectable por software anticheat)

## Licencia

**TODOS LOS DERECHOS RESERVADOS.**

Este software es propiedad privada. **NO se permite**:
- La redistribución del código fuente o ejecutables.
- La modificación del código para su distribución.
- El uso comercial de esta herramienta.

Para más detalles, consulta el archivo `LICENSE` incluido en este repositorio.

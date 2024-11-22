# Taller-Concurrencia
```
import asyncio

async def procesar_archivo(nombre):
    print(f"Procesando archivo: {nombre}")
    await asyncio.sleep(2)  # Simulación de 2 segundos sin bloqueo
    print(f"Archivo procesado: {nombre}")

async def procesar_archivos():
    archivos = ["archivo1.txt", "archivo2.txt", "archivo3.txt"]
    tareas = [procesar_archivo(archivo) for archivo in archivos]
    
    # Procesamos todos los archivos concurrentemente
    await asyncio.gather(*tareas)
    print("Todos los archivos han sido procesados.")

# Ejecutar el bucle de eventos
asyncio.run(procesar_archivos())

```

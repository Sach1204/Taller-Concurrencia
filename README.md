# Taller-Concurrencia
```
function procesarArchivo(nombre) {
  return new Promise((resolve) => {
    console.log(`Procesando archivo: ${nombre}`);
    setTimeout(() => {
      console.log(`Archivo procesado: ${nombre}`);
      resolve();
    }, 2000); // Simulación de 2 segundos sin bloqueo
  });
}

const archivos = ["archivo1.txt", "archivo2.txt", "archivo3.txt"];

async function procesarArchivos() {
  const promesas = archivos.map((archivo) => procesarArchivo(archivo));
  
  // Usamos Promise.all para procesar concurrentemente
  await Promise.all(promesas);

  console.log("Todos los archivos han sido procesados.");
}

// Ejecutamos la función principal
procesarArchivos();

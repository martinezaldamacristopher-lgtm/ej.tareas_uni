// ** CONFIGURACIÓN DEL SENSOR **
#include "DHT.h"

// Define el pin al que está conectado el cable de datos (DATA) del sensor DHT
#define DHTPIN 2 

// Define el tipo de sensor que estás usando (DHT11 o DHT22)
#define DHTTYPE DHT11 // Cambia a DHT22 si usas el modelo azul o blanco más preciso

// Inicializa el sensor DHT
DHT dht(DHTPIN, DHTTYPE);


void setup() {
  // Inicializa la comunicación serial para ver los datos
  Serial.begin(9600); 
  Serial.println("Inicializando sensor DHT...");
  
  // Inicia el sensor DHT
  dht.begin();
}


void loop() {
  // Esperamos 2 segundos entre lecturas (el DHT no puede leer más rápido)
  delay(2000); 

  // Lectura de humedad y temperatura
  float humedad = dht.readHumidity();
  float temperatura = dht.readTemperature();

  // Verificación de errores: si las lecturas no son números válidos (NaN), hubo un error
  if (isnan(humedad) || isnan(temperatura)) {
    Serial.println("Error al leer el sensor. Revisa las conexiones.");
    return; // Detiene la ejecución del loop y comienza de nuevo
  }

  // --- IMPRESIÓN DE RESULTADOS ---

  // Imprime Humedad
  Serial.print("Humedad: ");
  Serial.print(humedad);
  Serial.println(" %");

  // Imprime Temperatura
  Serial.print("Temperatura: ");
  Serial.print(temperatura);
  Serial.println(" *C");
  
  Serial.println("--------------------");
}

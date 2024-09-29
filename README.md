<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Proyecto Arduino - Código</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 20px;
        }
        h1 {
            color: #2C3E50;
        }
        pre {
            background-color: #f4f4f4;
            padding: 15px;
            border-radius: 5px;
            overflow-x: auto;
        }
        code {
            color: #e74c3c;
        }
    </style>
</head>
<body>
    <h1>Código del Proyecto Arduino</h1>
    <p>Este es el código utilizado para el proyecto de control de LEDs:</p>

    <pre><code>
// Configuración de pines
void setup() {
    for (int i = 2; i <= 13; i++) pinMode(i, OUTPUT);
}

// Loop principal
void loop() {
    // Modo 1: Parpadeo de LEDs
    for (int i = 2; i <= 10; i++) digitalWrite(i, HIGH);
    for (int i = 0; i < 10; i++) {
        int state = (i % 2 == 0) ? LOW : HIGH;
        for (int j = 11; j <= 13; j++) digitalWrite(j, state);
        delay(100);
    }

    // Modo 2: Encender filas una por una
    for (int i = 2; i <= 13; i++) digitalWrite(i, LOW);
    for (int j = 0; j <= 1; j++) {
        for (int i = 2; i <= 10; i++) {
            digitalWrite(i, HIGH); delay(100); digitalWrite(i, LOW); delay(100);
        }
    }

    // Modo 3: Encender capas una por una
    for (int i = 2; i <= 10; i++) digitalWrite(i, HIGH);
    for (int j = 0; j <= 4; j++) {
        for (int i = 11; i <= 13; i++) {
            digitalWrite(i, LOW); delay(100); digitalWrite(i, HIGH); delay(100);
        }
    }
}
    </code></pre>
</body>
</html>

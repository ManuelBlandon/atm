🏧 ATM Simulator - Sistema de Cajero Automático
Un simulador completo de cajero automático desarrollado para demostrar las operaciones bancarias fundamentales con una interfaz intuitiva y segura.
🎯 Descripción General
Este proyecto implementa un sistema de cajero automático (ATM) que simula todas las operaciones esenciales de un banco real. El sistema permite a los usuarios realizar transacciones bancarias de manera segura, con autenticación robusta y validaciones completas.
🌟 Objetivo del Proyecto
Crear una aplicación educativa y funcional que demuestre:

Principios de programación orientada a objetos
Manejo seguro de datos financieros
Implementación de sistemas de autenticación
Gestión de transacciones bancarias
Arquitectura de software escalable

⚡ Características Principales
🔐 Seguridad

Autenticación PIN: Sistema de verificación con número de tarjeta y PIN
Bloqueo de cuenta: Protección contra intentos de acceso no autorizados
Encriptación de datos: Protección de información sensible
Timeouts de sesión: Cierre automático por inactividad

💰 Operaciones Bancarias

Consulta de saldo: Verificación instantánea del balance actual
Retiro de efectivo: Extracción de dinero con validaciones de límites
Depósito de dinero: Ingreso de efectivo a la cuenta
Transferencias: Envío de dinero entre cuentas
Historial de transacciones: Registro detallado de todas las operaciones
Cambio de PIN: Actualización segura del código de acceso

🎨 Interfaz de Usuario

Menús intuitivos: Navegación clara y sencilla
Validaciones en tiempo real: Feedback inmediato al usuario
Mensajes informativos: Guías claras para cada operación
Manejo de errores: Respuestas amigables ante problemas

🚀 Instalación y Configuración
📋 Requisitos Previos
bash# Para Python
Python 3.8 o superior
pip (gestor de paquetes)

# Para Java
JDK 11 o superior
Maven 3.6 o superior

# Para C++
GCC 9.0 o superior
CMake 3.16 o superior
📦 Instalación Paso a Paso

Clonar el repositorio
bashgit clone https://github.com/ManuelBlandon/atm.git
cd atm

Configurar el entorno
bash# Python
python -m venv venv
source venv/bin/activate  # En Windows: venv\Scripts\activate
pip install -r requirements.txt

# Java
mvn clean install

# C++
mkdir build && cd build
cmake ..
make

Inicializar la base de datos
bash# Crear esquema inicial
python scripts/init_database.py

# Cargar datos de prueba
python scripts/load_sample_data.py

Ejecutar la aplicación
bash# Python
python src/main.py

# Java
java -jar target/atm-simulator-1.0.jar

# C++
./build/atm_simulator


📖 Guía de Uso
🔑 Proceso de Autenticación
=======================================
      🏧 BIENVENIDO AL ATM SIMULATOR
=======================================

Por favor, inserte su tarjeta...
Número de tarjeta: [16 dígitos]
PIN: [4 dígitos]

[✓] Autenticación exitosa
[✗] Credenciales inválidas - Intente nuevamente
🏠 Menú Principal
=======================================
           MENÚ PRINCIPAL
=======================================
Titular: Juan Pérez
Cuenta: ****1234

1. 💰 Consultar Saldo
2. 💸 Retirar Dinero
3. 💳 Depositar Dinero
4. 🔄 Transferir Dinero
5. 📄 Ver Historial
6. 🔧 Cambiar PIN
7. 🚪 Salir

Seleccione una opción [1-7]:
💡 Ejemplos de Operaciones
Consulta de Saldo
=======================================
         CONSULTA DE SALDO
=======================================
Saldo actual: $2,350.75
Saldo disponible: $2,100.75
Saldo retenido: $250.00

Última transacción: Depósito $150.00
Fecha: 2024-03-15 14:30:25
Retiro de Efectivo
=======================================
          RETIRO DE EFECTIVO
=======================================
Saldo disponible: $2,100.75

Montos disponibles:
1. $20     2. $50     3. $100
4. $200    5. $500    6. Otro monto

Límite diario: $1,000.00
Retirado hoy: $150.00
Disponible: $850.00
Transferencia de Dinero
=======================================
       TRANSFERENCIA DE DINERO
=======================================
Cuenta destino: [Número de cuenta]
Monto a transferir: $[Cantidad]
Concepto: [Descripción opcional]

Comisión por transferencia: $2.50
Total a debitar: $[Monto + Comisión]

¿Confirmar transacción? [S/N]
🏗️ Arquitectura del Sistema
📁 Estructura del Proyecto
atm-simulator/
├── 📂 src/
│   ├── 📂 core/
│   │   ├── atm_controller.py      # Controlador principal
│   │   ├── account_manager.py     # Gestión de cuentas
│   │   ├── transaction_processor.py # Procesador de transacciones
│   │   └── security_manager.py    # Manejo de seguridad
│   ├── 📂 models/
│   │   ├── account.py            # Modelo de cuenta
│   │   ├── transaction.py        # Modelo de transacción
│   │   ├── user.py              # Modelo de usuario
│   │   └── card.py              # Modelo de tarjeta
│   ├── 📂 services/
│   │   ├── authentication.py    # Servicio de autenticación
│   │   ├── validation.py        # Servicio de validación
│   │   └── encryption.py        # Servicio de encriptación
│   ├── 📂 database/
│   │   ├── connection.py        # Conexión a base de datos
│   │   ├── queries.py           # Consultas SQL
│   │   └── migrations/          # Scripts de migración
│   ├── 📂 ui/
│   │   ├── console_interface.py # Interfaz de consola
│   │   ├── menu_handler.py      # Manejo de menús
│   │   └── display_utils.py     # Utilidades de visualización
│   └── main.py                  # Punto de entrada
├── 📂 tests/
│   ├── unit/                    # Tests unitarios
│   ├── integration/             # Tests de integración
│   └── fixtures/                # Datos de prueba
├── 📂 config/
│   ├── settings.py              # Configuraciones
│   └── database.yml             # Configuración de DB
├── 📂 docs/
│   ├── api_reference.md         # Referencia de API
│   ├── user_manual.md           # Manual de usuario
│   └── deployment.md            # Guía de despliegue
├── 📂 scripts/
│   ├── init_database.py         # Inicialización de DB
│   └── backup_data.py           # Respaldo de datos
└── 📂 resources/
    ├── sample_data.json         # Datos de ejemplo
    └── logos/                   # Recursos gráficos
🔧 Componentes Clave
Controlador ATM
pythonclass ATMController:
    def __init__(self):
        self.account_manager = AccountManager()
        self.security_manager = SecurityManager()
        self.transaction_processor = TransactionProcessor()
    
    def authenticate_user(self, card_number, pin):
        # Lógica de autenticación
        pass
    
    def process_transaction(self, transaction_type, amount):
        # Procesamiento de transacciones
        pass
Gestión de Cuentas
pythonclass AccountManager:
    def get_balance(self, account_id):
        # Obtener saldo de cuenta
        pass
    
    def update_balance(self, account_id, amount, transaction_type):
        # Actualizar saldo
        pass
🔧 Configuración Avanzada
⚙️ Variables de Entorno
bash# .env
# Configuración de Base de Datos
DB_HOST=localhost
DB_PORT=5432
DB_NAME=atm_database
DB_USER=atm_user
DB_PASSWORD=secure_password

# Configuración de Seguridad
ENCRYPTION_KEY=your_encryption_key_here
SESSION_TIMEOUT=300  # 5 minutos
MAX_PIN_ATTEMPTS=3
ACCOUNT_LOCKOUT_TIME=1800  # 30 minutos

# Límites de Transacciones
DAILY_WITHDRAWAL_LIMIT=1000.00
SINGLE_WITHDRAWAL_LIMIT=500.00
TRANSFER_FEE=2.50
MINIMUM_BALANCE=10.00

# Configuración de Logs
LOG_LEVEL=INFO
LOG_FILE=logs/atm.log
AUDIT_LOG_FILE=logs/audit.log
🗄️ Configuración de Base de Datos
sql-- Esquema de base de datos
CREATE TABLE users (
    id SERIAL PRIMARY KEY,
    first_name VARCHAR(50) NOT NULL,
    last_name VARCHAR(50) NOT NULL,
    email VARCHAR(100) UNIQUE,
    phone VARCHAR(15),
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);

CREATE TABLE accounts (
    id SERIAL PRIMARY KEY,
    user_id INT REFERENCES users(id),
    account_number VARCHAR(16) UNIQUE NOT NULL,
    balance DECIMAL(12,2) DEFAULT 0.00,
    account_type VARCHAR(20) DEFAULT 'CHECKING',
    status VARCHAR(20) DEFAULT 'ACTIVE',
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);

CREATE TABLE cards (
    id SERIAL PRIMARY KEY,
    account_id INT REFERENCES accounts(id),
    card_number VARCHAR(16) UNIQUE NOT NULL,
    pin_hash VARCHAR(255) NOT NULL,
    status VARCHAR(20) DEFAULT 'ACTIVE',
    expiry_date DATE,
    failed_attempts INT DEFAULT 0,
    locked_until TIMESTAMP NULL
);

CREATE TABLE transactions (
    id SERIAL PRIMARY KEY,
    account_id INT REFERENCES accounts(id),
    transaction_type VARCHAR(20) NOT NULL,
    amount DECIMAL(12,2) NOT NULL,
    description TEXT,
    balance_after DECIMAL(12,2),
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);
🧪 Testing y Calidad
🔍 Ejecución de Tests
bash# Tests unitarios
python -m pytest tests/unit/ -v

# Tests de integración
python -m pytest tests/integration/ -v

# Tests con cobertura de código
python -m pytest --cov=src --cov-report=html tests/

# Tests de rendimiento
python -m pytest tests/performance/ -v
📊 Casos de Prueba
Tests de Autenticación

✅ Login exitoso con credenciales válidas
✅ Rechazo de PIN incorrecto
✅ Bloqueo de cuenta después de múltiples intentos fallidos
✅ Desbloqueo automático después del tiempo establecido

Tests de Transacciones

✅ Retiro exitoso con saldo suficiente
✅ Rechazo de retiro con saldo insuficiente
✅ Validación de límites diarios
✅ Depósito exitoso
✅ Transferencia entre cuentas válidas

Tests de Seguridad

✅ Encriptación de PIN
✅ Timeout de sesión
✅ Validación de entrada de datos
✅ Prevención de inyección SQL

📈 Métricas de Calidad
bash# Cobertura de código objetivo: >90%
# Complejidad ciclomática: <10
# Líneas de código por función: <50
# Documentación: >80% de funciones documentadas
🔐 Seguridad y Mejores Prácticas
🛡️ Medidas de Seguridad Implementadas

Autenticación Robusta

Hash de PIN con salt único
Límite de intentos de autenticación
Bloqueo temporal de cuentas


Validación de Datos

Sanitización de entrada
Validación de tipos de datos
Prevención de inyección SQL


Auditoría y Logging

Registro de todas las transacciones
Logs de seguridad
Monitoreo de actividad sospechosa


Encriptación

Datos sensibles encriptados en reposo
Comunicación segura
Claves de encriptación rotativas



🚨 Consideraciones de Seguridad
python# Ejemplo de manejo seguro de PIN
import hashlib
import secrets

def hash_pin(pin, salt=None):
    if salt is None:
        salt = secrets.token_hex(16)
    
    pin_hash = hashlib.pbkdf2_hmac(
        'sha256',
        pin.encode('utf-8'),
        salt.encode('utf-8'),
        100000  # iteraciones
    )
    
    return salt + pin_hash.hex()

def verify_pin(pin, stored_hash):
    salt = stored_hash[:32]
    stored_pin_hash = stored_hash[32:]
    
    pin_hash = hashlib.pbkdf2_hmac(
        'sha256',
        pin.encode('utf-8'),
        salt.encode('utf-8'),
        100000
    )
    
    return pin_hash.hex() == stored_pin_hash
📊 Monitoreo y Analytics
📈 Métricas del Sistema

Transacciones por minuto: Monitoreo de carga
Tiempo de respuesta: Latencia de operaciones
Tasa de errores: Porcentaje de transacciones fallidas
Uso de memoria: Consumo de recursos
Intentos de autenticación: Detección de ataques

🔍 Logs Estructurados
json{
  "timestamp": "2024-03-15T14:30:25.123Z",
  "level": "INFO",
  "event": "transaction_completed",
  "account_id": "ACC123456",
  "transaction_type": "withdrawal",
  "amount": 100.00,
  "balance_after": 1450.75,
  "location": "ATM_001",
  "session_id": "ses_abc123"
}
🚀 Despliegue y Producción
🐳 Containerización con Docker
dockerfileFROM python:3.9-slim

WORKDIR /app

COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

COPY src/ ./src/
COPY config/ ./config/

EXPOSE 8080

CMD ["python", "src/main.py"]
☁️ Configuración de Producción
yaml# docker-compose.yml
version: '3.8'

services:
  atm-app:
    build: .
    ports:
      - "8080:8080"
    environment:
      - DB_HOST=postgres
      - DB_NAME=atm_prod
    depends_on:
      - postgres
      - redis

  postgres:
    image: postgres:13
    environment:
      - POSTGRES_DB=atm_prod
      - POSTGRES_USER=atm_user
      - POSTGRES_PASSWORD=secure_password
    volumes:
      - postgres_data:/var/lib/postgresql/data

  redis:
    image: redis:6-alpine
    command: redis-server --appendonly yes
    volumes:
      - redis_data:/data

volumes:
  postgres_data:
  redis_data:
🎯 Roadmap y Futuras Mejoras
📅 Versión 2.0 (Q2 2024)

 Interfaz Gráfica (GUI)

Implementación con Tkinter/PyQt
Diseño responsive y moderno
Soporte para pantallas táctiles


 Autenticación Biométrica

Reconocimiento de huella dactilar
Reconocimiento facial
Autenticación de voz


 Funcionalidades Avanzadas

Pagos de servicios públicos
Recarga de celulares
Consulta de inversiones



📅 Versión 2.1 (Q3 2024)

 Integración con APIs Externas

Conexión con bancos reales
APIs de conversión de moneda
Servicios de notificación


 Aplicación Móvil

App complementaria para iOS/Android
Notificaciones push
Geo-localización de ATMs



📅 Versión 3.0 (Q4 2024)

 Inteligencia Artificial

Detección de fraude en tiempo real
Análisis predictivo de comportamiento
Chatbot de asistencia


 Blockchain Integration

Transacciones descentralizadas
Smart contracts
Criptomonedas



🤝 Contribución al Proyecto
📝 Guías de Contribución

Fork del Repositorio
bashgit clone https://github.com/TU_USUARIO/atm.git
cd atm
git remote add upstream https://github.com/ManuelBlandon/atm.git

Crear Rama de Trabajo
bashgit checkout -b feature/nueva-funcionalidad

Hacer Cambios y Commits
bashgit add .
git commit -m "feat: agregar nueva funcionalidad de X"

Push y Pull Request
bashgit push origin feature/nueva-funcionalidad


🔄 Convenciones de Commit
feat: nueva funcionalidad
fix: corrección de bug
docs: cambios en documentación
style: formateo, punto y coma faltante, etc.
refactor: refactorización de código
test: agregar tests faltantes
chore: tareas de mantenimiento
👥 Proceso de Code Review

Automatizado: Tests y linting deben pasar
Manual: Revisión por al menos un maintainer
Criterios: Código limpio, documentación actualizada, tests incluidos

📞 Soporte y Comunidad
🆘 Obtener Ayuda

GitHub Issues: Para bugs y solicitudes de funcionalidades
GitHub Discussions: Para preguntas generales y ideas
Wiki: Documentación extendida y tutoriales
Email: manuel.blandon@email.com

🌟 Reconocimientos

Contribuidores: Ver CONTRIBUTORS.md
Inspiración: Sistemas ATM de Banco Nacional
Librerías: Agradecimientos a la comunidad open source

📄 Licencia y Términos
Este proyecto está licenciado bajo la Licencia MIT - ver el archivo LICENSE para detalles completos.
📖 Resumen de la Licencia

✅ Uso comercial: Permitido
✅ Modificación: Permitida
✅ Distribución: Permitida
✅ Uso privado: Permitido
⚠️ Responsabilidad: Limitada
⚠️ Garantía: No incluida


<div align="center">
🏆 ATM Simulator - Educación Financiera a Través del Código
Desarrollado con ❤️ por Manuel Blandón

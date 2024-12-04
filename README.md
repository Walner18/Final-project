#  Spotify Clone
Una aplicación desarrollada en Flutter que utiliza Firebase como backend e implementa la Clean Architecture para garantizar modularidad, escalabilidad y mantenibilidad. Este proyecto simula las principales funcionalidades de Spotify y es ideal para aprender a construir aplicaciones complejas y bien estructuradas.
---

## Características

- **Autenticación:**
  - Registro e inicio de sesión de usuarios con Firebase.
  - Recuperación de usuarios autenticados.
  
- **Gestión de canciones:**
  - Agregar o quitar canciones de favoritos.
  - Ver listas de reproducción personalizadas.
  - Obtener las canciones más recientes.

- **Interfaz moderna:**
  - Soporte para tema claro y oscuro.
  - Pantalla de inicio animada (Splash).

- **Persistencia de estado:**
  - Manejo de estado con **Hydrated Bloc**.
  - Persistencia de datos local con `path_provider`.

- **Arquitectura modular:**
  - Separación en capas: `data`, `domain`, y `presentation`.
  - Inyección de dependencias con **GetIt**.

---

## Estructura del proyecto

```plaintext
lib/
├── core/
│   ├── errors/               # Manejo de excepciones
│   ├── usecases/             # Casos de uso genéricos
│   └── utils/                # Utilidades (helpers, constantes)
├── features/
│   ├── auth/                 # Módulo de autenticación
│   │   ├── data/             # Fuentes de datos de Firebase
│   │   ├── domain/           # Entidades y casos de uso
│   │   └── presentation/     # Widgets y lógica de UI
│   └── other_feature/        # Otros módulos organizados de forma similar
├── injection_container.dart  # Inyección de dependencias
└── main.dart                 # Punto de entrada


---

## Requisitos
Para ejecutar la aplicación en tu entorno local, asegúrate de tener lo siguiente:

Flutter instalado.
Dart instalado.
Un emulador o dispositivo físico para ejecutar la aplicación.
##  Contribuciones

¡Las contribuciones son bienvenidas! Si tienes ideas o encuentras algún problema, abre un issue o envía un pull request.

---
##Instalación
Clona este repositorio en tu máquina local:

git clone https://github.com/tu-usuario/tienda-electronica-flutter.git
Navega a la carpeta del proyecto: cd tienda-electronica-flutter

Instala las dependencias del proyecto: flutter pub get

Ejecuta la aplicación: flutter run

##  Autor
  Walner Comprès Holguìn 2021-0252

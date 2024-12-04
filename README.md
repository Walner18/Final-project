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

## 📂 Estructura del proyecto

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

## ⚙️ Configuración del proyecto

### 1. **Requisitos previos**

- [Flutter](https://docs.flutter.dev/get-started/install)
- [Firebase CLI](https://firebase.google.com/docs/cli)
- Un proyecto configurado en [Firebase Console](https://console.firebase.google.com/).

### 2. **Configurar Firebase**

1. Descarga el archivo `google-services.json` (para Android) y/o `GoogleService-Info.plist` (para iOS) desde tu consola de Firebase.
2. Coloca el archivo en las ubicaciones correspondientes:
   - Android: `android/app/google-services.json`.
   - iOS: `ios/Runner/GoogleService-Info.plist`.

### 3. **Instalar dependencias**

Ejecuta los siguientes comandos para instalar las dependencias necesarias:
```bash
flutter pub get
```

## 🌈 Temas y diseño

El proyecto incluye un sistema de temas claros y oscuros configurados en `core/configs/theme/app_theme.dart`. Puedes alternar entre ellos usando `ThemeCubit` con Bloc.

```dart
child: BlocBuilder<ThemeCubit, ThemeMode>(
  builder: (context, mode) => MaterialApp(
    theme: AppTheme.lightTheme,
    darkTheme: AppTheme.darkTheme,
    themeMode: mode,
    home: const SplashPage(),
  ),
),
```

---

##  Ejecución

Ejecuta el proyecto en tu emulador o dispositivo físico:
```bash
flutter run
```

Para habilitar el modo de producción, construye la aplicación con:
```bash
flutter build apk
```

---

##  Contribuciones

¡Las contribuciones son bienvenidas! Si tienes ideas o encuentras algún problema, abre un issue o envía un pull request.

---

## 📜 Autor
  Walner Comprès Holguìn 2021-0252

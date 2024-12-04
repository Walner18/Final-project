# 🎵 Spotify Clone

---

## 🚀 Características

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
├── common/                # Componentes comunes reutilizables
├── core/                  # Configuraciones globales (temas, rutas, etc.)
├── data/                  # Fuentes de datos y repositorios
├── domain/                # Casos de uso y contratos de repositorios
├── presentation/          # UI y lógica de presentación (Bloc)
│   ├── firebase_options.dart  # Configuración de Firebase
│   ├── main.dart              # Punto de entrada de la aplicación
│   └── service_locator.dart   # Configuración de inyección de dependencias
```

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

### 4. **Inicializar Firebase**

El archivo `firebase_options.dart` ya está configurado automáticamente con la CLI de Firebase. Solo asegúrate de que Firebase se inicializa en el método `main`:
```dart
await Firebase.initializeApp(
  options: DefaultFirebaseOptions.currentPlatform,
);
```

---

## 🛠️ Dependencias principales

Estas son las dependencias clave utilizadas en este proyecto:

- **Flutter Bloc**: Manejo de estados reactivos.
- **Hydrated Bloc**: Persistencia de estados local.
- **GetIt**: Inyección de dependencias.
- **Firebase Core & Auth**: Autenticación y servicios backend.
- **Path Provider**: Acceso al sistema de archivos del dispositivo.

```yaml
dependencies:
  flutter:
    sdk: flutter
  flutter_bloc: ^8.1.2
  hydrated_bloc: ^9.1.0
  firebase_core: ^2.11.0
  firebase_auth: ^4.5.0
  path_provider: ^2.0.11
  get_it: ^7.6.0
```

---

## 🌟 Arquitectura

El proyecto sigue el patrón de **Clean Architecture**, dividiendo la lógica en capas:

### **1. Data Layer:**
- Fuentes de datos y servicios (Firebase, API externas).
- Implementaciones de repositorios.

### **2. Domain Layer:**
- Casos de uso (lógica de negocio independiente de la UI).
- Contratos de repositorios (interfaces).

### **3. Presentation Layer:**
- Widgets y pantallas.
- Gestión de estados con Bloc.

---

## 💡 Uso del Service Locator

El archivo `service_locator.dart` centraliza la configuración de dependencias. Ejemplo de registro de un repositorio y un caso de uso:

```dart
sl.registerSingleton<AuthRepository>(
  AuthRepositoryImpl(),
);

sl.registerSingleton<SignupUseCase>(
  SignupUseCase(),
);
```

Llama a `initializeDependencies()` en el método `main` para configurar todo antes de iniciar la aplicación.

---

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

## 🖥️ Ejecución

Ejecuta el proyecto en tu emulador o dispositivo físico:
```bash
flutter run
```

Para habilitar el modo de producción, construye la aplicación con:
```bash
flutter build apk
```

---

## 🤝 Contribuciones

¡Las contribuciones son bienvenidas! Si tienes ideas o encuentras algún problema, abre un issue o envía un pull request.

---

## 📜 Autor
  ¡

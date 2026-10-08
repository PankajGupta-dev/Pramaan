# PRAMAAN

PRAMAAN turns an Android smartphone into a verifiable fitness-testing station using on-device AI pose tracking, hardware-backed Android Keystore signatures, and physics checks.

## Project Structure

- `:app` - Android application (Jetpack Compose, Material 3, CameraX, MediaPipe)
- `:core` - Pure Kotlin/JVM library (scoring, integrity engine, canonical JSON, cryptographic verification)
- `:server` - Ktor JVM application (Netty server on port 8080, SQLite database, verification API & dashboard)

## Prerequisites

- JDK 17
- Android SDK (minSdk 26, compileSdk/targetSdk 36)

## Quick Start

### Run Core Tests
```bash
./gradlew :core:test
```

### Build Android App
```bash
./gradlew :app:assembleDebug
```

### Run Verification Server
```bash
./gradlew :server:run
```
The server starts at `http://localhost:8080`.

## Demo Checklist

1. Add athlete (name, age, sex, height)
2. Record standing vertical jump (3 attempts, live skeleton overlay)
3. Instant result with physics checks (Verified badge)
4. Offline witness co-signing via QR (Witnessed badge)
5. Sync session to server
6. Verify certificate via QR
7. Test cheat detection with simulated edit / slow-motion import

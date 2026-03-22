# Flutter BLoC Clean Architecture

![Flutter](https://img.shields.io/badge/Flutter-3.x-02569B?logo=flutter)
![Dart](https://img.shields.io/badge/Dart-3.x-0175C2?logo=dart)
![BLoC](https://img.shields.io/badge/State-BLoC-blue)
![Clean Architecture](https://img.shields.io/badge/Clean-Architecture-orange)
![Coverage](https://img.shields.io/badge/Coverage-80%25%2B-brightgreen)

A production-ready Flutter sample application demonstrating **BLoC pattern + Clean Architecture** with Dart, modular structure, and comprehensive test coverage.

---

## Architecture Overview

This project follows **Clean Architecture** with **BLoC** as the state management solution:

```
lib/
├── core/                        # Shared Core
│   ├── error/                   # Failures & Exceptions
│   ├── network/                 # Dio / HTTP client
│   ├── usecase/                 # Base UseCase interface
│   └── utils/                   # Extensions, Constants
│
├── features/                    # Feature-based modules
│   └── posts/                   # Example Feature
│       ├── data/
│       │   ├── datasource/      # Remote & Local data sources
│       │   ├── model/           # Data models + JSON serialization
│       │   └── repository/     # Repository implementations
│       │
│       ├── domain/
│       │   ├── entity/          # Domain entities (pure Dart)
│       │   ├── repository/      # Repository interfaces
│       │   └── usecase/         # Business logic use cases
│       │
│       └── presentation/
│           ├── bloc/            # BLoC (Events, States, Bloc)
│           ├── pages/           # Screens / Pages
│           └── widgets/         # Feature-specific widgets
│
└── injection_container.dart     # GetIt DI setup
```

---

## Tech Stack

| Layer | Technology |
|-------|-----------|
| Language | Dart 3.x |
| Framework | Flutter 3.x |
| State Management | flutter_bloc + BLoC pattern |
| DI | get_it + injectable |
| Networking | Dio + Retrofit |
| Local Storage | Hive / SharedPreferences |
| Navigation | go_router |
| JSON | json_serializable + freezed |
| Testing | flutter_test, bloc_test, mocktail |
| CI | GitHub Actions + Fastlane |
| Code Quality | flutter_lints, dart_code_metrics |

---

## Key Features

- Feature-first modular folder structure for scalability
- BLoC with sealed states using freezed for type-safety
- Repository pattern with Either (dartz) for error handling
- Offline-first with Hive local caching
- 80%+ test coverage across BLoCs, use cases, and repositories
- GitHub Actions CI running tests and Flutter analyze on every PR

---

## Testing Strategy

```
test/
├── core/                        # Core utility tests
├── features/
│   └── posts/
│       ├── data/                # Repository & datasource tests
│       ├── domain/              # Use case unit tests
│       └── presentation/       # BLoC tests (bloc_test)
└── helpers/                     # Mocks (mocktail), test fixtures
```

Run tests:
```bash
flutter test                              # All tests
flutter test --coverage                   # With coverage
genhtml coverage/lcov.info -o coverage/   # HTML coverage report
```

---

## CI/CD Pipeline

```yaml
# .github/workflows/flutter-ci.yml
- flutter analyze (lint)
- flutter test --coverage
- Coverage report upload
- Build APK (Android)
- Build IPA (iOS via Fastlane)
```

---

## Getting Started

1. Clone the repository
```bash
git clone https://github.com/radha-panda/flutter-bloc-clean-architecture.git
```

2. Install dependencies
```bash
flutter pub get
```

3. Generate code (freezed + json_serializable)
```bash
dart run build_runner build --delete-conflicting-outputs
```

4. Run the app
```bash
flutter run
```

---

## Author

**Radha Rani Panda** — Mobile Team Lead | 8+ Years Android/iOS/Flutter  
[LinkedIn](https://www.linkedin.com/in/radha-rani-panda-6754a2124/) · [GitHub](https://github.com/radha-panda)

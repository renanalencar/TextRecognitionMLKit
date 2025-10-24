# Agent Guidelines for TextRecognitionMLKit

## Build & Test Commands
- Build: `./gradlew build` or `./gradlew assembleDebug`
- Run tests: `./gradlew test` (unit tests) or `./gradlew connectedAndroidTest` (instrumented tests)
- Run single test: `./gradlew test --tests "com.android4you.textrecognition.ExampleUnitTest.addition_isCorrect"`
- Clean: `./gradlew clean`
- Lint: Detekt is enabled in IDE settings

## Code Style Guidelines
- **Language**: Kotlin with Compose UI
- **Package naming**: Use reverse domain `com.android4you.textrecognition.*`
- **Imports**: Group standard library imports first, then third-party, then project imports with blank lines between groups
- **Naming**: camelCase for variables/functions, PascalCase for classes/composables
- **Functions**: Use `fun` keyword, specify return types explicitly when not obvious
- **Composables**: Use `@Composable` annotation, PascalCase naming
- **Error handling**: Use try-catch blocks, log errors with `Log.e()`, provide user-friendly error messages
- **Dependencies**: Use version catalog (libs.versions.toml), prefer `implementation` over `api`
- **Object declarations**: Use `object` keyword for singletons/utility classes (like TextRecognitionHelper)
- **Null safety**: Use nullable types (`?`) appropriately, prefer safe calls (`?.`) over force unwrapping
- **Lambda expressions**: Use trailing lambda syntax when possible
- **String templates**: Use `${}` for complex expressions, `$` for simple variables
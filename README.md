# TextRecognitionMLKit

An Android application that uses Google ML Kit to extract text from images through camera capture or gallery selection.

## Features

- **Real-time Camera Preview**: Live camera feed with text capture functionality
- **Gallery Image Selection**: Choose images from device gallery for text extraction
- **ML Kit Text Recognition**: Powered by Google ML Kit for accurate text detection
- **Chinese Text Support**: Enhanced support for Chinese character recognition
- **Modern UI**: Built with Jetpack Compose and Material Design 3

## Screenshots

The app provides two main ways to extract text:
1. **Camera Capture**: Use the camera to capture images and extract text in real-time
2. **Gallery Selection**: Select existing images from your device gallery

## Requirements

- **Minimum SDK**: API 34 (Android 14)
- **Target SDK**: API 35
- **Compile SDK**: API 36
- **Camera Permission**: Required for camera functionality

## Tech Stack

- **Language**: Kotlin
- **UI Framework**: Jetpack Compose
- **Architecture**: MVVM with Compose
- **ML Framework**: Google ML Kit
- **Camera**: CameraX
- **Build System**: Gradle with Kotlin DSL
- **Minimum Android Version**: Android 14 (API 34)

## Dependencies

### Core Dependencies
- **Jetpack Compose**: Modern UI toolkit
- **CameraX**: Camera functionality and lifecycle management
- **ML Kit Text Recognition**: Text extraction from images
- **Material Design 3**: Modern design components

### Key Libraries
```kotlin
// ML Kit
implementation("com.google.mlkit:text-recognition:16.0.1")
implementation("com.google.mlkit:text-recognition-chinese:16.0.1")

// CameraX
implementation("androidx.camera:camera-camera2:1.4.2")
implementation("androidx.camera:camera-lifecycle:1.3.0")
implementation("androidx.camera:camera-view:1.3.0")

// Jetpack Compose
implementation(platform("androidx.compose:compose-bom:2025.04.00"))
implementation("androidx.compose.ui:ui")
implementation("androidx.compose.material3:material3")
```

## Setup and Installation

### Prerequisites
- Android Studio Hedgehog or later
- JDK 11 or higher
- Android SDK with API 34+

### Clone and Build
```bash
git clone https://github.com/yourusername/TextRecognitionMLKit.git
cd TextRecognitionMLKit
./gradlew build
```

### Run the App
```bash
./gradlew assembleDebug
./gradlew installDebug
```

## Usage

1. **Grant Camera Permission**: The app will request camera permission on first launch
2. **Camera Mode**: 
   - Point your camera at text
   - Tap "Capture" to take a photo and extract text
3. **Gallery Mode**:
   - Tap "Select Image from Gallery"
   - Choose an image containing text
   - Text will be automatically extracted and displayed

## Project Structure

```
app/src/main/java/com/android4you/textrecognition/
├── MainActivity.kt                    # Main activity with Compose UI
├── ui/theme/                         # Theme and styling
│   ├── Color.kt
│   ├── Theme.kt
│   └── Type.kt
└── util/
    └── TextRecognitionHelper.kt      # ML Kit text recognition logic
```

## Key Components

### MainActivity
- Handles camera permissions
- Manages UI state for recognized text
- Integrates camera preview and gallery selection

### TextRecognitionHelper
- Utility class for ML Kit text recognition
- Supports both Latin and Chinese text recognition
- Processes images from URIs and returns extracted text

### CameraBox Composable
- Custom camera preview component
- Handles image capture and processing
- Styled with rounded corners and proper aspect ratio

## Permissions

The app requires the following permission:
- `CAMERA`: For camera functionality and image capture

## Build Commands

```bash
# Clean build
./gradlew clean

# Debug build
./gradlew assembleDebug

# Release build
./gradlew assembleRelease

# Run tests
./gradlew test

# Run instrumented tests
./gradlew connectedAndroidTest
```

## Configuration

### Text Recognition Languages
The app currently supports:
- **Latin scripts** (English, etc.)
- **Chinese characters** (Simplified and Traditional)

To modify language support, update the recognizer in `TextRecognitionHelper.kt`:

```kotlin
// For Latin text only
val recognizer = TextRecognition.getClient(TextRecognizerOptions.DEFAULT_OPTIONS)

// For Chinese text (current configuration)
val recognizer = TextRecognition.getClient(
    ChineseTextRecognizerOptions.Builder().build()
)
```

## Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/new-feature`)
3. Commit your changes (`git commit -am 'Add new feature'`)
4. Push to the branch (`git push origin feature/new-feature`)
5. Create a Pull Request

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Acknowledgments

- [Google ML Kit](https://developers.google.com/ml-kit) for text recognition capabilities
- [CameraX](https://developer.android.com/training/camerax) for camera functionality
- [Jetpack Compose](https://developer.android.com/compose) for modern UI development

## Support

For issues and questions:
1. Check existing [GitHub Issues](https://github.com/yourusername/TextRecognitionMLKit/issues)
2. Create a new issue with detailed description
3. Include device information and Android version

---

**Note**: This app requires Android 14 (API 34) or higher due to the modern camera and ML Kit requirements.
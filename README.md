# SeniorScamShield 🛡️

**SeniorScamShield** is an Android application designed to protect older adults from phone scams, robocalls, and fraudulent threats. By leveraging Android's native `CallScreeningService` and custom overlay displays, the app intercepts unknown callers before they ring and displays high-contrast, easy-to-read warnings requiring safe-word verification.

---

## 🌟 Key Features

* **Automated Call Interception:** Intercepts incoming calls silently at the system level. Known scam numbers are hung up on automatically (`setRejectCall(true)`).
* **High-Contrast Warning Overlay:** Displays an accessible, large-text warning banner over unknown incoming calls using Android's `WindowManager`.
* **Family Safe-Word Verification:** Prompts unknown callers or users for a pre-configured family safe-word before proceeding.
* **Biometric & Guardian Security:** Protects sensitive security settings and whitelist/blacklist updates using Android PIN/Biometric authentication (`BiometricAuthManager`).
* **Senior-Friendly UI:** Designed with Jetpack Compose, featuring high contrast, large typography, and zero clutter.

---

## 📐 Project Architecture & Structure

SeniorScamShield/
├── app/
│   ├── src/
│   │   └── main/
│   │       ├── AndroidManifest.xml
│   │       └── java/com/example/seniorscamshield/
│   │           ├── MainActivity.kt                # Runtime permissions setup & UI host
│   │           ├── ScamScreeningService.kt        # Intercepts & handles incoming system calls
│   │           ├── OverlayService.kt              # Foreground service for drawing overlay banner
│   │           ├── CallWarningOverlay.kt          # Jetpack Compose UI for high-contrast alerts
│   │           ├── ContactLabelChecker.kt         # Evaluates phone numbers against contact lists
│   │           ├── BiometricAuthManager.kt        # System PIN / Fingerprint protection
│   │           └── GuardianNotifier.kt            # Handles guardian notifications
│   └── build.gradle.kts
├── build.gradle.kts
└── settings.gradle.kts


---

## ⚙️ Prerequisites & Tech Stack

* **Language:** Kotlin
* **UI Framework:** Jetpack Compose (Material 3)
* **Minimum SDK:** API 26 (Android 8.0 Oreo)
* **Target SDK:** API 34+
* **Key Dependencies:**
  * `androidx.telecom` (Call Screening Service)
  * `androidx.biometric:biometric`
  * `androidx.room` & SQLCipher (Encrypted local storage)

---

## 🚀 Setup & Installation

1. **Clone the Repository:**
   ```bash
   git clone [https://github.com/YOUR_USERNAME/SeniorScamShield.git](https://github.com/YOUR_USERNAME/SeniorScamShield.git)
   cd SeniorScamShield

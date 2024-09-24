# Calculator Automation with Maestro

## About The Project
This repository contains test automation for the Calculator mobile app using YAML and the Maestro framework. The project is structured using the Page Object Model and organized into test suites to ensure maintainability and scalability.

## Table of Contents
- [About The Project](#about-the-project)
- [Getting Started](#getting-started)
  - [Prerequisites](#prerequisites)
  - [Installation](#installation)
- [Executing Tests](#executing-tests)
  - [Run Tests by Filename](#run-tests-by-filename)
  - [Run Tests by Tags](#run-tests-by-tags)
  - [Execute Tests on a Specific Device with Debug Logs](#execute-tests-on-a-specific-device-with-debug-logs)
  - [Execute UAT Tests on a Specific Device](#execute-uat-tests-on-a-specific-device)
  - [Execute Tests on any Available Device](#execute-tests-on-any-available-device)
- [Additional Commands](#additional-commands)
- [Directory Structure](#directory-structure)
- [Contributing](#contributing)
- [License](#license)
- [Contact](#contact)

## Getting Started

### Prerequisites
Make sure you have the following installed:
- **Java Development Kit (JDK)**
- **Android Studio** with SDK tools
- **Maestro CLI**

Refer to the [Maestro installation guide](https://maestro.mobile.dev/getting-started/installing-maestro) for detailed setup instructions.

### Installation
Clone the repository to get started:

```bash
git clone https://github.com/YourUsername/calculator-automation.git
cd calculator-automation
```
Executing Tests
Run Tests by Filename
Execute specific test cases on a device for the Calculator app:

```shell
maestro test -e APK_PATH="/Users/YourUsername/Downloads/Calculator.apk" -e DEVICE_ID=4a55444957393498 --format JUNIT tests/calculator_test.maestro.yml
```

Run Tests by Tags
Run tests based on tags (useful for grouping tests like "smoke" or "regression"):

```shell
maestro test -e APK_PATH="/Users/YourUsername/Downloads/Calculator.apk" -e DEVICE_ID=4a55444957393498 --format JUNIT --include-tags=regression tests/
```

Execute Tests on a Specific Device with Debug Logs
Run tests on a specific device and generate detailed execution logs:

```shell
maestro --device 4a55444957393498 test -e APK_PATH="/Users/YourUsername/Downloads/Calculator.apk" --format JUNIT --debug-output logs/debug-logs/ tests/
```

Execute UAT Tests on a Specific Device
Run UAT tests using specific tags and generate execution logs:

```shell
maestro --device 4a55444957393498 test -e APK_PATH="/Users/YourUsername/Downloads/Calculator.apk" --format JUNIT --include-tags=uat --debug-output logs/debug-logs/ tests/
```
Execute Tests on any Available Device
Run the test suite on any connected device, capturing both the test results and logs:

```shell
maestro test -e APK_PATH="/Users/YourUsername/Downloads/Calculator.apk" --format JUNIT --debug-output logs/debug-logs/ tests/
```

Additional Commands
View Available Devices
List all connected devices to identify the device ID:

```shell
adb devices
Uninstall the App (if needed)
```
Remove the Calculator app from your device before reinstalling:

```shell
adb -s 4a55444957393498 uninstall com.google.android.calculator
```

Directory Structure
```
bk-mobile-tests/
├── android/
│   ├── calculator/
│   │   └── perform_addition.yaml
│   ├── splash/
│   │   └── splash.yaml
│   └── tests/
│       └── calculator-tests.maestro.yaml
├── package.json
└── README.md
calculator/: Contains test scripts related to calculator functionalities.
splash/: Includes tests for splash screen functionalities.
tests/: Contains the main test suite files for execution.
```

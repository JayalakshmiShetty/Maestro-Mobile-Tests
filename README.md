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
git clone https://github.com/JayalakshmiShetty/Maestro-Mobile-Tests.git
```
Executing Tests
Run Tests by Filename with Debug Logs
Execute specific test cases on a device/Emulator for the Calculator app and generate detailed execution logs:

```shell
maestro --device emulator-5554 test -e APP_ID=com.google.android.calculator --format junit --debug-output debug-logs/ android"

maestro test -e APP_ID=com.google.android.calculator -e DEVICE_ID=4a55444957393498 --format junit --debug-output debug-logs/ android",

```

Run Tests by Tags
Run tests based on tags (useful for grouping tests like "smoke" or "regression"):

```shell

maestro test -e APP_ID=com.google.android.calculator -e DEVICE_ID=4a55444957393498 --format junit --include-tags=regression android

```

Execute Tests on any Available Device
Run the test suite on any connected device, capturing both the test results and logs:

```shell
maestro test -e APP_ID=com.google.android.calculator --format JUNIT --debug-output debug-logs/ android

```

To Execute all tests from package.json
```
npm run test:calculation:all
```

To Record video for tests from package.json
```
npm run test:record:addition
npm run test:record:subtraction
npm run test:record:multiplication
npm run test:record:division
```

Additional Commands
View Available Devices
List all connected devices to identify the device ID:

```shell
adb devices
```
Uninstall the App (if needed)
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
│   ├── test-data/
│   │   └── test-data.json
│   └── tests/
│       └── calculator-tests.yaml
├── package.json
└── README.md
└── report.xml

calculator/: Contains test scripts related to calculator functionalities.
splash/: Includes tests for splash screen functionalities.
tests/: Contains the main test suite files for execution.
```
**NOTE** : To enable execution in Maestro Cloud, I have removed the tests/ folder because all flows need to be at the same directory level.

### 🏃🏽 How to run the tests on Maestro Cloud
1. Open the terminal in the project root directory and login to the CLI by running this command.
   
   ```
   maestro login
   ```
   > Sign in using your email address then the login link will be sent over to complete the process. If this is your first time logging in, you'll be prompted to create an account. Follow the printed instructions to complete the login process.
2. Run your flow on Maestro Cloud with this command.
   ```
   maestro cloud -e APP_ID=<APP_ID> APP_ID=com.google.android.calculator --apiKey=<API_KEY> --app-file=app/Calculator.apk android"'

   ```
   ![maestro-cloud-terminal](https://github.com/marizala/maestro-automation/assets/37069334/5c862851-9cea-4c4a-ac5c-24e77c29bc70)

   ![maestro-cloud](https://github.com/marizala/maestro-automation/assets/37069334/2082d15d-294d-4c03-8e7b-9b1afbba6f3e)

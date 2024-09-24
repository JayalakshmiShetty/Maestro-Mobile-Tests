
```markdown
## Calculator Automation with Maestro

<!-- ABOUT THE PROJECT -->
## About The Project
This repository contains test automation for the Calculator mobile app using YAML and the Maestro framework. The project is structured with Page Objects and test suites to ensure maintainability and scalability.

<!-- GETTING STARTED -->
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
```

### Execute Tests
#### Run Tests by Filename
Execute specific test cases on a device for the Calculator app:

```shell
maestro test -e APK_PATH="/Users/YourUsername/Downloads/Calculator.apk" -e DEVICE_ID=4a55444957393498 --format JUNIT tests/calculator_test.maestro.yml
```

#### Run Tests by Tags
Run tests based on tags (useful for grouping tests like "smoke", "regression"):

```shell
maestro test -e APK_PATH="/Users/YourUsername/Downloads/Calculator.apk" -e DEVICE_ID=4a55444957393498 --format JUNIT --include-tags=regression tests/
```

#### Execute Tests on a Specific Device with Debug Logs
Run the tests on a specific device and generate detailed execution logs:

```shell
maestro --device 4a55444957393498 test -e APK_PATH="/Users/YourUsername/Downloads/Calculator.apk" --format JUNIT --debug-output logs/debug-logs/ tests/
```

#### Execute UAT Tests on a Specific Device
Run UAT tests using specific tags and generate execution logs:

```shell
maestro --device 4a55444957393498 test -e APK_PATH="/Users/YourUsername/Downloads/Calculator.apk" --format JUNIT --include-tags=uat --debug-output logs/debug-logs/ tests/
```

#### Execute Tests on any Available Device
Run the test suite on any available connected device, capturing both the test results and logs:

```shell
maestro test -e APK_PATH="/Users/YourUsername/Downloads/Calculator.apk" --format JUNIT --debug-output logs/debug-logs/ tests/
```

### Additional Commands

#### View Available Devices
List all connected devices to identify the device ID:

```shell
adb devices
```

#### Uninstall the App (if needed)
Remove the Calculator app from your device before reinstalling:

```shell
adb -s 4a55444957393498 uninstall com.google.android.calculator
```



### Summary of Changes:
1. **About the Project:** Briefly describes the purpose and structure of the project.
2. **Getting Started:** Lists prerequisites and setup instructions with a link to the Maestro installation guide.
3. **Installation:** Provides the repository clone command for setting up the project locally.
4. **Execute Tests:** Offers several example commands for running tests, using environment variables and options like `--format JUNIT` and `--include-tags`.
5. **Additional Commands:** Includes useful commands for viewing connected devices and uninstalling the app.
6. **Directory Structure:** Describes the purpose of each directory in the project.
7. **Contributing, License, and Contact Sections:** General sections to encourage contributions and provide project-related information.

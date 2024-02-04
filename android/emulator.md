# Configure Android Virtual Device without Android Studio on macOS

## Installation

First, make sure that `openjdk` is installed. If not, install most recent
release with

```
brew install java
```

Then install android commandlinetools with

```
brew install android-commandlinetools
```

## Download Android Tools

```
sdkmanager platform-tools emulator
```

## Setup environment variables

```
export ANDROID_SDK_ROOT="/opt/homebrew/share/android-commandlinetools/"
export PATH="/opt/homebrew/share/android-commandlinetools/emulator:$PATH"
export PATH="/opt/homebrew/share/android-commandlinetools/platform-tools:$PATH"
export PATH="/opt/homebrew/share/android-commandlinetools/build-tools/34.0.0:$PATH"
```

## Download packages

Download Android Software Development Kit(SDK) with following command

```
sdkmanager "platforms;android-34"
```

Download Android build tools

```
sdkmanager "build-tools;34.0.0"
```

Download Android system image
```
sdkmanager "system-images;android-34;google_apis;arm64-v8a"
```

## Create an Android Virtual Device

```
avdmanager create avd --name mydevice --package "system-images;android-34;google_apis;arm64-v8a"
```

## Start Android Virtual Device

```
emulator -avd mydevice
```

# Expo Constants.deviceName Inconsistencies on Android

This repository demonstrates a bug encountered when using the `Constants.deviceName` API in Expo.  On certain Android devices or emulators, the API may return an empty string or `null`, rather than the expected device name.

## Problem

The `Constants.deviceName` API, intended to retrieve the device's name, exhibits inconsistent behavior.  This inconsistency can break device-specific code or produce erroneous results. The provided `bug.js` file shows the problem where `deviceName` could be null or empty, leading to potential crashes or unexpected application behavior.

## Solution

The `bugSolution.js` file offers a solution to mitigate this problem.  It introduces a safeguard, checking for null or empty strings and providing a fallback value (in this case, 'Unknown Device'). This ensures the application gracefully handles unexpected return values from `Constants.deviceName`.

## How to Reproduce

1. Clone this repository.
2. Navigate to the directory: `cd expo-device-name-bug`
3. Install dependencies: `npm install`
4. Run the project: `expo start`
5. Observe the output in the console. On some Android emulators, it will display 'Device Name: null' or 'Device Name: ' indicating the issue.

## Usage

Examine `bug.js` to understand how the original problem arises, and use `bugSolution.js` to implement a robust solution.  This demonstrates good practices for handling potential inconsistencies when working with platform-specific APIs.
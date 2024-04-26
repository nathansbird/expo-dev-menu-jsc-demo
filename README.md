Expo app cannot compile for iPhone Simulator 17.4 with using Expo 51 beta, latest expo-dev-client, and JSC. Have not tested using a device SDK instead of the Simulator SDK.

**Steps to reproduce:**
1. Initialize a new project with SDK 51 beta: `npx create-expo-app@latest --template default@beta`
2. Specify `jsc` as the iOS or project `jsEngine`
3. Install latest expo-dev-client: `npx expo install expo-dev-client`
4. Attempt to run the app `npx expo run:ios --device`

Note: tying down the `expo-dev-menu` version to `5.0.3` via resolutions in package.json clears the issue. I think it is reasonable to assume this commit is the problematic one: https://github.com/expo/expo/commit/616efad308dc1d52713989a00a68aebdc4270092

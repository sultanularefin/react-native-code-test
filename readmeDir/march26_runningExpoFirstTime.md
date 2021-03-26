

1. npm i -g expo-cli

1. taxi@taxi-HP-ProBook-4540s:~/Programs/react-native-code-test$ sudo yarn global add expo-cli

2. https://reactnavigation.org/docs/getting-started/
2. expo install react-native-gesture-handler react-native-reanimated react-native-screens react-native-safe-area-context @react-native-community/masked-view

3.   "@react-native-firebase/app": "^11.1.2",
    "@react-native-firebase/auth": "^11.1.2",


4. 

package.json file :::

```json

{
  "main": "node_modules/expo/AppEntry.js",
  "private": true,
  "scripts": {
    "start": "expo start",
    "android": "expo start --android",
    "ios": "expo start --ios",
    "web": "expo start --web",
    "eject": "expo eject",
    "ios2": "react-native run-ios --device 'Arefin_have_no_MAC'",
    "test": "jest",
    "lint": "eslint ."
  },
  "dependencies": {
    "@eva-design/eva": "^2.0.0",
    "@react-native-async-storage/async-storage": "^1.14.1",
    "@react-native-community/masked-view": "0.1.10",
    "@react-native-community/netinfo": "^6.0.0",
    "@react-native-firebase/app": "^11.1.2",
    "@react-native-firebase/auth": "^11.1.2",
    "@react-native-firebase/firestore": "^11.1.2",
    "@react-native-picker/picker": "^1.12.0",
    "@react-navigation/drawer": "^5.12.4",
    "@react-navigation/material-top-tabs": "^5.3.14",
    "@react-navigation/native": "^5.9.3",
    "@react-navigation/stack": "^5.14.3",
    "@ui-kitten/components": "^5.0.0",
    "dayjs": "^1.10.4",
    "expo": "^40.0.1",
    "expo-font": "^9.0.0",
    "expo-status-bar": "^1.0.3",
    "lottie-react-native": "~2.6.1",
    "moment": "^2.29.1",
    "react": "17.0.1",
    "react-dom": "^17.0.2",
    "react-native": "0.64.0",
    "react-native-gesture-handler": "~1.8.0",
    "react-native-mmkv": "^1.1.6",
    "react-native-pager-view": "^5.1.2",
    "react-native-reanimated": "~1.13.0",
    "react-native-safe-area-context": "3.1.9",
    "react-native-screens": "~2.15.2",
    "react-native-snackbar": "^2.4.0",
    "react-native-svg": "12.1.0",
    "react-native-tab-view": "^3.0.0",
    "react-native-web": "~0.13.12"
  },
  "devDependencies": {
    "@babel/core": "^7.13.10",
    "@babel/runtime": "^7.13.10",
    "@react-native-community/eslint-config": "^2.0.0",
    "@types/jest": "^26.0.21",
    "@types/react": "^17.0.3",
    "@types/react-dom": "^17.0.3",
    "@types/react-native": "^0.64.0",
    "@types/react-test-renderer": "^17.0.1",
    "babel-jest": "^26.6.3",
    "eslint": "^7.22.0",
    "jest": "^26.6.3",
    "metro-react-native-babel-preset": "^0.65.2",
    "react-test-renderer": "17.0.1",
    "typescript": "^4.2.3"
  },
  "jest": {
    "preset": "react-native"
  }
}

```


## complete App.tsx file march 26::

```js

import { StatusBar } from "expo-status-bar";
import React from "react";

import { StyleSheet,
  View } from "react-native";

import * as eva from "@eva-design/eva";

import { ApplicationProvider, Text } from "@ui-kitten/components";

import mapping from "./mapping.json";
import { useFonts } from "expo-font";

const App = () => {
  const [loaded, error] = useFonts({
    Roboto: require("./assets/fonts/Roboto/Roboto.ttf"),
    "Roboto-Bold": require("./assets/fonts/Roboto/Roboto-Bold.ttf"),
  });

  if (!loaded) {
    return null;
  }

  return (
    <ApplicationProvider
      {...eva}
      theme={eva.light}
      customMapping={{ ...eva.mapping, ...mapping }}
    >
      <View style={styles.container}>
        <Text style={styles.titleText} category="h1">
          Do your best and enjoy the process!
        </Text>
        <StatusBar style="auto" />
      </View>
    </ApplicationProvider>
  );
};

export default App;

const styles = StyleSheet.create({
  container: {
    flex: 1,
    backgroundColor: "#fff",
    alignItems: "center",
    justifyContent: "center",
  },
  titleText: {
    textAlign: "center",
  },
});

```
# react-native-zendesk
React Native bridge to Zendesk Support SDK v2 on iOS and Android. 

## Installation
1. Add the package via yarn or npm
```
yarn add react-native-zendesk
npm install --save react-native-zendesk
```

2. Link the modules to your native projects
```
react-native link react-native-zendesk
```

3. For your iOS app, add Zendesk SDK 2 via Pod, add this to your pod `pod 'ZendeskSDK'`, then `pod install`

4. For your iOS app, add a Run Script build phase to your app target to strip the extra architectures from the Zendesk frameworks, with the following script:

`bash "${BUILT_PRODUCTS_DIR}/${FRAMEWORKS_FOLDER_PATH}/ZendeskCoreSDK.framework/strip-frameworks.sh"`

## Getting Started
### Initializing the Support SDK (Required)
```js
const config = {
  zendeskUrl: ZENDESK_URL,
  appId: ZENDESK_APP_ID,
  clientId: ZENDESK_CLIENT_ID,
};

Zendesk.initialize(config);
```

### Setting an identity (Required)

#### Setting an anonymous identity
```js
Zendesk.identifyAnon();
Zendesk.identifyAnon(USER_NAME, USER_EMAIL);
```

#### Setting a unique identity
```js
Zendesk.identifyJWT(USER_TOKEN);
```

### Adding Help Center
```ts
// possible options to pass to the help center
interface Options {
  hideContactSupport?: boolean
}

Zendesk.showHelpCenter(OPTIONS);
```

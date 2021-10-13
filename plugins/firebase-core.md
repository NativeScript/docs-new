---
title: 'Core'
link: https://raw.githubusercontent.com/NativeScript/firebase/main/packages/firebase-core/README.md
---

### ![github logo]('../assets/images/github/GitHub-Mark-32px.png'): [Core](https://github.com/NativeScript/firebase/tree/main/packages/firebase-core)

# @nativescript/firebase-core

```javascript
ns plugin add @nativescript/firebase-core
```

## Usage

### Initialize Default App

```ts
import { Firebase } from '@nativescript/firebase-core'
const firebase = Firebase.initializeApp()
```

### Initialize Secondary App

```ts
import { Firebase } from '@nativescript/firebase-core'
const config = new FirebaseOptions()
const firebase = Firebase.initializeApp(config, 'SECONDARY_APP')
```

## License

Apache License Version 2.0

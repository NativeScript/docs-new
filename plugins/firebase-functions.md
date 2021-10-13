---
title: 'Functions'
link: https://raw.githubusercontent.com/NativeScript/firebase/main/packages/firebase-functions/README.md
---

# Repo: [Functions](https://github.com/NativeScript/firebase/tree/main/packages/firebase-functions)

# @nativescript/firebase-functions

```javascript
ns plugin add @nativescript/firebase-functions
```

## What does it do

Firebase Cloud Functions let you automatically run backend code in response to events triggered by Firebase features and HTTPS requests. Your code is stored in Google's cloud and runs in a managed environment. There's no need to manage and scale your own servers.

[![image](https://img.youtube.com/vi/vr0Gfvp5v1A/hqdefault.jpg)](https://www.youtube.com/watch?v=vr0Gfvp5v1A)

After you write and deploy a function, Google's servers begin to manage the function immediately. You can fire the function directly with an HTTP request, via the Cloud Functions module, or in the case of background functions, Google's servers will listen for events and run the function when it is triggered.

For more information on use cases, view the [Firebase Cloud Functions](https://firebase.google.com/docs/functions/use-cases) documentation.

## Usage

The Cloud Functions module provides the functionality to directly trigger deployed HTTPS callable functions, without worrying about security or implementing a HTTP request library.

Functions deployed to Firebase have unique names, allowing you to easily identify which endpoint you wish to send a request to. To learn more about deploying Functions to Firebase, view the Writing & Deploying Functions documentation.

## Calling an endpoint

Assuming we have a deployed a callable endpoint named listProducts, to call the endpoint the library exposes a httpsCallable method. For example:

```ts
// Deployed HTTPS callable
exports.listProducts = functions.https.onCall(() => {
  return [
    /* ... */
    // Return some data
  ]
})
```

Within the application, the list of products returned can be directly accessed:

```ts
import { firebase } from '@nativescript/firebase-core'
import '@nativescript/firebase-functions'
firebase()
  .functions()
  .httpsCallable('listProducts')()
  .then(response => {
    setProducts(response.data)
    setLoading(false)
  })
```

## Using an emulator

Whilst developing your application with Cloud Functions, it is possible to run the functions inside of a local emulator.

To call the emulated functions, call the useEmulator method exposed by the library:

```ts
import { firebase } from '@nativescript/firebase-core'
firebase().functions().useEmulator('localhost', 5000)
```

## License

Apache License Version 2.0

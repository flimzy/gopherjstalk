# Integrating with existing JS libraries

There are two approaches:

- Expose your Go code to JavaScript

    To integrate a specific Go library into a larger JavaScript app.

    The **MakeWrapper()** function allows a Go struct to be seen as a standard JavaScript object by JavaScript code.

- Wrap JavaScript libraries in Go

    For projects written primarily in Go which need to communicate with an existing JavaScript library. For instance, to manipulate the DOM, access Local Storage, or use Web Workers.

    The **js** library allows direct access to underlying JavaScript objects from Go code.

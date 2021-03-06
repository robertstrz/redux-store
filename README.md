# Redux store implementation
A simple Redux store implementation in vanilla JS, tailored for a workshop.
This repository gives you a set of tests that ensure basic functionality of Redux Store is implemented.

> At its core, Redux is really a fairly simple design pattern: all your "write" logic goes into a single function, and the only way to run that logic is to give Redux a plain object that describes something that has happened.  The Redux store calls that write logic function and passes in the current state tree and the descriptive object, the write logic function returns some new state tree, and the Redux store notifies any subscribers that the state tree has changed.
[- Redux page](https://redux.js.org)

## Preliminaries

* Clone the repository
* Install [Node v8.9.4](https://nodejs.org/en/) (LTS)
* Run `npm install` in the project directory so that all dependencies are installed
* Run `npm test` to run tests for the store and check if your implementation is correct

## Test Cases

* `should create a store` - it ensures that Store class is implemented and that it sets `state` property to some default value (e.g. empty object)
* `should create a store with some initial state` - the Store is extended, it allows passing initial state and stores it
* `should create a store with initial state and reducers` - the Store is now able to set both initial state (if provided) and reducers
* `should dispatch an action to a reducer` - the Store should implement `dispatch` method that will call a reducer with an action passed
* `should dispatch an action to all reducers` - the Store should actually dispatch an action to all reducers
* `should dispatch an action to reducers and update state` - the Store dispatch method should build a new state based on return values of all reducers and update the current state
* `should dispatch an action to reducers and update state immutably` - the Store should not mutate neither the state nor the action
* `should notify subscribers on state update` - the Store should implement `subscribe` method that will accept a listener function, that will be called on `dispatch`. It also should return unsubscribe function, that (if called) will remove the listener.

# promise-fun

I intend to use this space to document my promise modules, useful promise patterns, and how to solve common problems. For now though, you can see all my promise modules below.

## Contents

- [Packages](#packages)
- [FAQ](#faq)

## Packages

*Not accepting additions, but happy to take requests.*

- **[pify](https://github.com/sindresorhus/pify)**: Promisify a callback-style function
- **[delay](https://github.com/sindresorhus/delay)**: Delay a promise a specified amount of time
- **[yoctodelay](https://github.com/sindresorhus/yoctodelay)**: Delay a promise a specified amount of time
- **[p-map](https://github.com/sindresorhus/p-map)**: Map over promises concurrently
- **[p-all](https://github.com/sindresorhus/p-all)**: Run promise-returning & async functions concurrently with optional limited concurrency
- **[p-queue](https://github.com/sindresorhus/p-queue)**: Promise queue with concurrency control
- **[p-event](https://github.com/sindresorhus/p-event)**: Promisify an event by waiting for it to be emitted
- **[p-debounce](https://github.com/sindresorhus/p-debounce)**: Debounce promise-returning & async functions
- **[p-throttle](https://github.com/sindresorhus/p-throttle)**: Throttle promise-returning & async functions
- **[p-timeout](https://github.com/sindresorhus/p-timeout)**: Timeout a promise after a specified amount of time
- **[p-retry](https://github.com/sindresorhus/p-retry)**: Retry a promise-returning or async function
- **[p-any](https://github.com/sindresorhus/p-any)**: Wait for any promise to be fulfilled
- **[p-some](https://github.com/sindresorhus/p-some)**: Wait for a specified number of promises to be fulfilled
- **[p-locate](https://github.com/sindresorhus/p-locate)**: Get the first fulfilled promise that satisfies the provided testing function
- **[p-limit](https://github.com/sindresorhus/p-limit)**: Run multiple promise-returning & async functions with limited concurrency
- **[p-series](https://github.com/sindresorhus/p-series)**: Run promise-returning & async functions in series
- **[p-memoize](https://github.com/sindresorhus/p-memoize)**: Memoize promise-returning & async functions
- **[p-pipe](https://github.com/sindresorhus/p-pipe)**: Compose promise-returning & async functions into a reusable pipeline
- **[p-props](https://github.com/sindresorhus/p-props)**: Like `Promise.all()` but for `Map` and `Object`
- **[p-waterfall](https://github.com/sindresorhus/p-waterfall)**: Run promise-returning & async functions in series, each passing its result to the next
- **[p-cancelable](https://github.com/sindresorhus/p-cancelable)**: Create a promise that can be canceled
- **[p-progress](https://github.com/sindresorhus/p-progress)**: Create a promise that reports progress
- **[p-reflect](https://github.com/sindresorhus/p-reflect)**: Make a promise always fulfill with its actual fulfillment value or rejection reason
- **[p-filter](https://github.com/sindresorhus/p-filter)**: Filter promises concurrently
- **[p-reduce](https://github.com/sindresorhus/p-reduce)**: Reduce a list of values using promises into a promise for a value
- **[p-settle](https://github.com/sindresorhus/p-settle)**: Settle promises concurrently and get their fulfillment value or rejection reason
- **[p-every](https://github.com/kevva/p-every)**: Test whether all promises passes a testing function
- **[p-one](https://github.com/kevva/p-one)**: Test whether some promise passes a testing function
- **[p-map-series](https://github.com/sindresorhus/p-map-series)**: Map over promises serially
- **[p-each-series](https://github.com/sindresorhus/p-each-series)**: Iterate over promises serially
- **[p-times](https://github.com/sindresorhus/p-times)**: Run promise-returning & async functions a specific number of times concurrently
- **[p-lazy](https://github.com/sindresorhus/p-lazy)**: Create a lazy promise that defers execution until `.then()` or `.catch()` is called
- **[p-whilst](https://github.com/sindresorhus/p-whilst)**: While a condition returns true, calls a function repeatedly, and then resolves the promise
- **[p-do-whilst](https://github.com/sindresorhus/p-do-whilst)**: Calls a function repeatedly while a condition returns true and then resolves the promise
- **[p-forever](https://github.com/sindresorhus/p-forever)**: Run promise-returning & async functions repeatedly until you end it
- **[p-wait-for](https://github.com/sindresorhus/p-wait-for)**: Wait for a condition to be true
- **[p-min-delay](https://github.com/sindresorhus/p-min-delay)**: Delay a promise a minimum amount of time
- **[p-try](https://github.com/sindresorhus/p-try)**: `Promise.try()` ponyfill - Starts a promise chain
- **[p-race](https://github.com/sindresorhus/p-race)**: A better `Promise.race()`
- **[p-immediate](https://github.com/sindresorhus/p-immediate)**: Returns a promise resolved in the next event loop - think `setImmediate()`
- **[p-time](https://github.com/sindresorhus/p-time)**: Measure the time a promise takes to resolve
- **[p-defer](https://github.com/sindresorhus/p-defer)**: Create a deferred promise
- **[p-is-promise](https://github.com/sindresorhus/p-is-promise)**: Check if something is a promise
- **[p-state](https://github.com/sindresorhus/p-state)**: Inspect the state of a promise
- **[make-synchronous](https://github.com/sindresorhus/make-synchronous)**: Make an asynchronous function synchronous

### `.then`/`.catch`-based packages

*You should generally avoid using `.then` except in edge cases.*

- **[p-catch-if](https://github.com/sindresorhus/p-catch-if)**: Conditional promise catch handler
- **[p-if](https://github.com/sindresorhus/p-if)**: Conditional promise chains
- **[p-tap](https://github.com/sindresorhus/p-tap)**: Tap into a promise chain without affecting its value or state
- **[p-log](https://github.com/sindresorhus/p-log)**: Log the value/error of a promise
- **[p-break](https://github.com/sindresorhus/p-break)**: Break out of a promise chain

## FAQ

### How can I run 100 async/promise-returning functions with only 5 running at once?

This is a good use-case for [`p-map`](https://github.com/sindresorhus/p-map). You might ask why you can't just specify an array of promises. Promises represent values of a computation and not the computation itself - they are eager. So by the time `p-map` starts reading the array, all the actions creating those promises have already started running. `p-map` works by executing a promise-returning function in a mapper function. This way the promises are created lazily and can be concurrency limited. Check out [`p-all`](https://github.com/sindresorhus/p-all) instead if you're using different functions to get each promise.

```js
const pMap = require('p-map');

const urls = [
	'https://sindresorhus.com',
	'https://avajs.dev',
	'https://github.com',
	…
];

console.log(urls.length);
//=> 100

const mapper = url => fetchStats(url); //=> Promise

const result = await pMap(urls, mapper, {concurrency: 5});

console.log(result);
//=> [{url: 'https://sindresorhus.com', stats: {…}}, …]
```

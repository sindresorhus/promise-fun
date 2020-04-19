# promise-fun [![Gitter](https://badges.gitter.im/join_chat.svg)](https://gitter.im/promisefun/Lobby)

I intend to use this space to document my promise modules, useful promise patterns, and how to solve common problems. For now though, you can see all my promise modules below.

## Contents

- [Packages](#packages)
- [FAQ](#faq)

## Packages

*Not accepting additions, but happy to take requests.*

- **[pify](https://github.com/sindresorhus/pify)**: Promisify a callback-style function
- **[delay](https://github.com/sindresorhus/delay)**: Delay a promise a specified amount of time
- **[p-map](https://github.com/sindresorhus/p-map)**: Map over promises concurrently
- **[p-all](https://github.com/sindresorhus/p-all)**: Run promise-returning & async functions concurrently with optional limited concurrency
- **[p-queue](https://github.com/sindresorhus/p-queue)**: Promise queue with concurrency control
- **[p-catch-if](https://github.com/sindresorhus/p-catch-if)**: Conditional promise catch handler
- **[p-if](https://github.com/sindresorhus/p-if)**: Conditional promise chains
- **[p-tap](https://github.com/sindresorhus/p-tap)**: Tap into a promise chain without affecting its value or state
- **[p-log](https://github.com/sindresorhus/p-log)**: Log the value/error of a promise
- **[p-event](https://github.com/sindresorhus/p-event)**: Promisify an event by waiting for it to be emitted
- **[p-debounce](https://github.com/sindresorhus/p-debounce)**: Debounce promise-returning & async functions
- **[p-throttle](https://github.com/sindresorhus/p-throttle)**: Throttle promise-returning & async functions
- **[p-timeout](https://github.com/sindresorhus/p-timeout)**: Timeout a promise after a specified amount of time
- **[p-finally](https://github.com/sindresorhus/p-finally)**: `Promise#finally()` ponyfill - Invoked when the promise is settled regardless of outcome
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
- **[p-break](https://github.com/sindresorhus/p-break)**: Break out of a promise chain
- **[p-is-promise](https://github.com/sindresorhus/p-is-promise)**: Check if something is a promise
- **[loud-rejection](https://github.com/sindresorhus/loud-rejection)**: Make unhandled promise rejections fail loudly instead of the default silent fail
- **[hard-rejection](https://github.com/sindresorhus/hard-rejection)**: Make unhandled promise rejections fail hard right away instead of the default silent fail

## FAQ

### How can I run 100 async/promise-returning functions with only 5 running at once?

This is a good use-case for [`p-map`](https://github.com/sindresorhus/p-map). You might ask why you can't just specify an array of promises. Promises represent values of a computation and not the computation itself - they are eager. So by the time `p-map` starts reading the array, all the actions creating those promises have already started running. `p-map` works by executing a promise-returning function in a mapper function. This way the promises are created lazily and can be concurrency limited. Check out [`p-all`](https://github.com/sindresorhus/p-all) instead if you're using different functions to get each promise.

```js
const pMap = require('p-map');

const urls = [
	'sindresorhus.com',
	'ava.li',
	'github.com',
	…
];

console.log(urls.length);
//=> 100

const mapper = url => {
	return fetchStats(url); //=> Promise
};

pMap(urls, mapper, {concurrency: 5}).then(result => {
	console.log(result);
	//=> [{url: 'sindresorhus.com', stats: {…}}, …]
});
```

### How can I reduce nesting?

Let's say you want to fetch some data, process it, and return both the data and the processed data.

The common approach would be to nest the promises:

```js
const getData = id =>
	Storage
		.find(id)
		.then(data => {
			return process(data).then(result => {
				return prepare(data, result);
			});
		});
```

But we can take advantage of `Promise.all`:

```js
const getData = id =>
	Storage
		.find(id)
		.then(data => Promise.all([data, process(data)])
		.then(([data, result]) => prepare(data, result));
```

And even simpler with [async functions](https://www.2ality.com/2016/02/async-functions.html): *(Requires Babel or Node.js 8)*

```js
const getData = async id => {
	const data = await Storage.find(id);
	return prepare(data, await process(data));
};
```

### What about something like [`Bluebird#spread()`](http://bluebirdjs.com/docs/api/spread.html)?

Bluebird:

```js
Promise.resolve([1, 2]).spread((one, two) => {
	console.log(one, two);
	//=> 1 2
});
```

Instead, use [destructuring](https://developer.mozilla.org/en/docs/Web/JavaScript/Reference/Operators/Destructuring_assignment):

```js
Promise.resolve([1, 2]).then(([one, two]) => {
	console.log(one, two);
	//=> 1 2
});
```

### What about something like [`Bluebird.join()`](http://bluebirdjs.com/docs/api/promise.join.html)?

Bluebird:

```js
Promise.join(p1, p2, p3, (r1, r2, r3) => {
	// …
});
```

Instead, use an [async function](https://jakearchibald.com/2014/es7-async-functions/) and [destructuring](https://developer.mozilla.org/en/docs/Web/JavaScript/Reference/Operators/Destructuring_assignment):

```js
const [r1, r2, r3] = await Promise.all([p1, p2, p3]);
// …
```

### How do I break out of a promise chain?

You might think you want to break out ("return early") when doing conditional logic in promise chains.

Here you would like to only run the `onlyRunConditional` promises if `conditional` is truthy.

```js
alwaysRun1()
	.then(() => alwaysRun2())
	.then(conditional => conditional || somehowBreakTheChain())
	.then(() => onlyRunConditional1())
	.then(() => onlyRunConditional2())
	.then(() => onlyRunConditional3())
	.then(() => onlyRunConditional4())
	.then(() => alwaysRun3());
```

You could implement the above by [abusing the promise rejection mechanism](https://github.com/sindresorhus/p-break). However, it would be better to branch out the chain instead. Promises can not only be chained, but also nested and unnested.

```js
const runConditional = () =>
	onlyRunConditional1()
		.then(() => onlyRunConditional2())
		.then(() => onlyRunConditional3())
		.then(() => onlyRunConditional4());

alwaysRun1()
	.then(() => alwaysRun2())
	.then(conditional => conditional && runConditional())
	.then(() => alwaysRun3());
```

# [jquery-mutation-summary](https://joelpurra.com/projects/jquery-mutation-summary/) javascript library

<p class="donate">
  <a href="https://joelpurra.com/donate/proceed/?amount=5&currency=usd"><kbd>Donate $5 now</kbd></a>
  <a href="https://joelpurra.com/donate/proceed/?amount=25&currency=usd"><kbd>Donate $25 now</kbd></a>
  <a href="https://joelpurra.com/donate/proceed/?amount=100&currency=usd&invoice=true"><kbd>Donate $100 now</kbd></a>
  <a href="https://joelpurra.com/donate/"><kbd>More options</kbd></a>
</p>

A jQuery wrapper/plugin for mutation-summary, the DOM mutation-observers wrapper. It adds easy, chainable `.mutationSummary()` calls to your jQuery objects.

> [Mutation Summary](https://github.com/rafaelw/mutation-summary) is a JavaScript library that makes observing changes to the DOM fast, easy and safe.

The Mutation Summary library aggregates multiple DOM mutations to a neat changeset, optionally [filtered by CSS-style selectors](https://github.com/rafaelw/mutation-summary/blob/master/APIReference.md#The_element_Query). Have a look at [this fun and informative 8 minute screen cast](https://www.youtube.com/watch?v=eRZ4pO0gVWw) by [Rafael Z Weinstein](https://github.com/rafaelweinstein), the creator of mutation-summary.

- [Project page](https://joelpurra.com/projects/jquery-mutation-summary/)
- [Source on Github](https://github.com/joelpurra/jquery-mutation-summary)



## Get it

- [`jquery.mutation-summary.js`](src/jquery.mutation-summary.js)



## Demos

* [`example/shuffle.html`](https://joelpurra.com/projects/jquery-mutation-summary/docs/example/shuffle.html): A copy of the original [shuffle.html example](https://github.com/rafaelw/mutation-summary/blob/master/examples/shuffle_compare/shuffle.html), but with this library as the default option. Shuffle.html is explained in [the mutation-summary screen cast](https://github.com/rafaelw/mutation-summary).
* [`example/demo.html`](https://joelpurra.com/projects/jquery-mutation-summary/docs/example/demo.html): Listening to simple mutations in a list.



## Usage

See [mutation-summary API reference](https://github.com/rafaelw/mutation-summary/blob/master/APIReference.md) for details on [`callback(summary[])`](https://github.com/rafaelw/mutation-summary/blob/master/APIReference.md#callback-parameters), [`queries`](https://github.com/rafaelw/mutation-summary/blob/master/APIReference.md#query-types) and other options.


### Public methods

```javascript
// Connect mutation observation
$(selector).mutationSummary("connect", options);
$(selector).mutationSummary("connect", callback(summary[]) [, observeOwnChanges], queries);

// Diconnect all mutation observation
$(selector).mutationSummary("disconnect");

// To disconnect a previous "connect" call only, pass the same parameters
$(selector).mutationSummary("disconnect", options);
$(selector).mutationSummary("disconnect", callback(summary[]) [, observeOwnChanges], queries);
```


### Example

```javascript
// Use document to listen to all events on the page (you might want to be more specific)
var $observerSummaryRoot = $(document);

// Simplest callback, just logging to the console
function callback(summaries){
	console.log(summaries);
}

// Connect mutation-summary
$observerSummaryRoot.mutationSummary("connect", callback, [{ all: true }]);

// Do something to trigger mutationSummary
$("<a />", { href: "https://joelpurra.com/projects/jquery-mutation-summary/"}).text("Go to the jquery-mutation-summary website").appendTo("body");

// Disconnect when done listening
$observerSummaryRoot.mutationSummary("disconnect");
```



## Original purpose

Developed to get a jQuery chainable version of the mutation-summary library.

[DOM Mutation Observers](https://dom.spec.whatwg.org/#mutation-observers) are useful for watching changes made to the DOM elements (including their attributes and contents) that are out of your control. These external changes may come from other jQuery plugins, non-jQuery scripts, legacy code or even flash objects that modifies the page around it.
If you have previously used [DOM Mutation Events](https://github.com/rafaelw/mutation-summary/blob/master/DOMMutationObservers.md), please note that they have been deprecated.



## Dependencies

jquery-mutation-summary's runtime dependencies are

* [mutation-summary](https://github.com/rafaelw/mutation-summary)
* [jQuery](https://jquery.com/)



## Browser compatibility

Should be as compatible as mutation-summary is - see the wiki page on [browser support for Mutation Observers](https://github.com/rafaelw/mutation-summary/blob/master/DOMMutationObservers.md#browser-availability) as well as [caniuse.com/mutationobserver](http://caniuse.com/mutationobserver). jQuery is assumed to be available in these environments.



## TODO

*Patches/pull requests welcome!*

* Write tests.
* Write example callback filters that act only on, for example, removed attributes or added elements.
* Add support for [namespaced/filtered events](https://api.jquery.com/event.namespace/), for example `mutationSummary.element.added` or `mutationSummary.attribute.valueChanged`.



---



[jquery-mutation-summary](https://joelpurra.com/projects/jquery-mutation-summary/) copyright (c) 2012, 2013, 2014, 2015, 2016, 2017, [Joel Purra](https://joelpurra.com/). All rights reserved. When using jquery-mutation-summary, comply to at least one of the three available licenses: BSD, MIT, GPL. [Your donations are appreciated!](https://joelpurra.com/donate/)

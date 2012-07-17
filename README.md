# [jquery-mutation-summary](http://joelpurra.github.com/jquery-mutation-summary) javascript library
A jQuery wrapper/plugin for mutation-summary, the DOM mutation-observers wrapper.

> [Mutation Summary](http://code.google.com/p/mutation-summary/) is a JavaScript library that makes observing changes to the DOM fast, easy and safe.

## Get it

To include dependencies, make sure to get the submodules too.

```
git clone --recursive git://github.com/joelpurra/jquery-mutation-summary.git
```

## Demos
* [`example/shuffle.html`](http://joelpurra.github.com/jquery-mutation-summary/example/shuffle.html): A copy of the original [shuffle.html example](http://mutation-summary.googlecode.com/git/examples/shuffle_compare/shuffle.html), but with this library as the default option.
* [`example/demo.html`](http://joelpurra.github.com/jquery-mutation-summary/example/demo.html): Simple listening to different changes in two lists.

## Usage

### Javascript

```javascript
// Use windows to listen to all events on the page
var $observerSummaryRoot = $(window);

// Simplest callback, just logging to the console
function callback(summaries){
	console.log(summaries);
}

// Connect mutation-summary
$observerSummaryRoot.mutationSummary("connect", callback, [{ all: true }]);

// Do something to trigger mutationSummary
$("<a />", { href: "http://joelpurra.github.com/jquery-mutation-summary"}).text("Go to the jquery-mutation-summary website").appendTo("body");

// Disconnect when done listening
$observerSummaryRoot.mutationSummary("disconnect");
```

## Original purpose
Developed to get a jQuery chainable version of the mutation-summary library.

## Dependencies
jquery-mutation-summary's runtime dependencies are

* [mutation-summary](https://code.google.com/p/mutation-summary/)
* [jQuery](http://jquery.com/)

## Browser compatibility
Should be about as compatible as mutation-summary is - see the wiki page on [browser support for Mutation Observers](http://code.google.com/p/mutation-summary/wiki/DOMMutationObservers#Browser_Availability).

## TODO
* Write tests.
* Write example callback filters.
* Add support for [namespaced/filtered events](http://docs.jquery.com/Namespaced_Events), for example `mutationSummary.element.added` or `mutationSummary.attribute.valueChanged`.

## License
Copyright (c) 2012, Joel Purra <http://joelpurra.se/>
All rights reserved.

When using CollectCalls, comply to at least one of the three available licenses: BSD, MIT, GPL.
Please see the LICENSE file for details.

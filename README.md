# examples

## Flux TodoMVC - LCARS and CargoBay

This is the example of flux todomvc using our [LCARS (implementation of facbook's dispatcher)](https://github.com/sstate/lcars) and [cargo-bay (base events for stores)](https://github.com/sstate/cargo-bay).

[[live demo](http://sstate.github.io/examples/examples/flux-todomvc/)]

To see the example, clone this repo

```

git clone git@github.com:sstate/examples.git

cd examples/flux-todomvc

npm install

npm run start

```

then open `examples/flux-todomvc/index.html` in your browser.

You can see that our implementation of facebook's flux _is_ facebook flux. We are not trying to re-create flux. With our
libraries and tools, you can easily follow facebook's guides and documentation. LCARS and cargo-bay are intently using
facebook's guides and designs, because we want to stay as close to their vision as possible.


## Flux TodoMVC - Freighter

This is the example of flux todomvc using our [Freighter](https://github.com/sstate/freighter) storage mixin for react components.

[[live demo](http://sstate.github.io/examples/examples/flux-todomvc-freighter/)]

For an example of how it might change the look of a component, here would be the diff from facebook's original code.

```
diff --git a/examples/flux-todomvc-freighter/js/components/TodoApp.react.js b/Users/rtorr/git/flux/examples/flux-todomvc/js/components/TodoApp.react.js
index cf2ed55..6d31a6f 100644
--- a/examples/flux-todomvc-freighter/js/components/TodoApp.react.js
+++ b/Users/rtorr/git/flux/examples/flux-todomvc/js/components/TodoApp.react.js
@@ -17,7 +17,6 @@ var Header = require('./Header.react');
 var MainSection = require('./MainSection.react');
 var React = require('react');
 var TodoStore = require('../stores/TodoStore');
-var Freighter = require('freighter');

 /**
  * Retrieve the current TODO data from the TodoStore
@@ -31,12 +30,16 @@ function getTodoState() {

 var TodoApp = React.createClass({

-  mixins: [Freighter],
+  getInitialState: function() {
+    return getTodoState();
+  },

-  stores: [TodoStore],
+  componentDidMount: function() {
+    TodoStore.addChangeListener(this._onChange);
+  },

-  getStateFromStores: function(){
-    return getTodoState();
+  componentWillUnmount: function() {
+    TodoStore.removeChangeListener(this._onChange);
   },

   /**
```

To see the example, clone this repo

```

git clone git@github.com:sstate/examples.git

cd examples/flux-todomvc-feighter

npm install

npm run start

```
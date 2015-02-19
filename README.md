# examples

## Flux TodoMVC

This is the example of flux todomvc using our [LCARS (implementation of facbook's dispatcher)](https://github.com/sstate/lcars) and [cargo-bay (base events for stores)](https://github.com/sstate/cargo-bay).

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

# pull-streams: there is a module for that!

## how can I achieve 1:many and many:1 transforms?

* use `pull(pull.map(mapToArray), pull.flatten())`
* use [pull-through](https://github.com/pull-stream/pull-through)

## how do I interop with node streams? are there any caveats?

* use [stream-to-pull-stream](https://github.com/pull-stream/stream-to-pull-stream)
  back pressure will still work correctly.
  make sure you use `toPull.source(readable)` `toPull.sink(writable)` or `toPull.duplex(duplex)`.

## is there a way I can push to a pull stream?

generally, avoid doing this if you can because you'll loose
back pressure, but if you must

* use [pull-pushable](https://github.com/pull-stream/pull-pushable)

## can i apply a async function over pull-stream input?

* use [pull-paramap](https://github.com/pull-stream/pull-paramap)
  order will be preserved.

## I need to return a stream immediately, but need to do something async first, how?

* use [pull-defer](https://github.com/pull-stream/pull-defer)

# can I concat two pull-streams

yes.

* use [pull-cat](https://github.com/pull-stream/pull-cat)

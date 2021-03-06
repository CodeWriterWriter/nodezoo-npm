![logo-nodezoo][Logo]

# nodezoo-npm

- __Lead:__ [Richard Rodger][Lead]
- __Sponsor:__ [nearForm][]

A micro-service that provides [npm][] data for [NodeZoo][]. This micro-service depends
on the npm registry but also caches retrieved data to reduce load on the public
registry.

If you're using this microservice, and need help, you can:

- Post a [github issue][],
- Tweet to [@nodezoo][],
- Ask on the [Gitter][gitter-url].


## Running
This micro-service can be ran as part of the [Nodezoo][] system. Please follow the
link below for details on obtaining and running the complete system.

- [Nodezoo: The complete system][System]

## Patterns Handled

### `role:npm,cmd:get`
Returns npm specific data for the module name provided.

```js
seneca.act(`role:npm,cmd:get`, {name:'seneca'})
```

### `role:info,req:part`
An alias for `role:npm,cmd:get`, allows integration into the wider nodezoo-system.

```js
seneca.act(`role:info,req:part`, {data: {name:'seneca', ...}})
```


## Patterns Emitted

### `role:info,res:part`

Called in response to a call to `role:info,req:part`.

```js
seneca.add(`role:info,res:part`, {data: {name:'seneca', ...}})
```

## Contributing
The [NodeZoo org][] encourages __open__ and __safe__ participation.

- __[Code of Conduct][CoC]__

If you feel you can help in any way, be it with documentation, examples, extra testing, or new
features please get in touch.


## License
Copyright (c) 2014 - 2016, Richard Rodger and other contributors.
Licensed under [MIT][].

[CoC]: https://github.com/nodezoo/nodezoo-org/blob/master/CoC.md
[Logo]: https://raw.githubusercontent.com/nodezoo/nodezoo-org/master/assets/logo-nodezoo.png
[NPM]: http://npmjs.org
[NodeZoo]: https://github.com/rjrodger/nodezoo
[nearForm]: http://nearform.com
[Lead]: https://github.com/rjrodger
[NodeZoo org]: https://github.com/nodezoo
[MIT]: ./LICENSE
[github issue]: https://github.com/nodezoo/nodezoo-npm/issues
[@nodezoo]: http://twitter.com/nodezoo
[gitter-url]: https://gitter.im/nodezoo/nodezoo-org
[System]: https://github.com/nodezoo/nodezoo-system

# Choose Dependency Injection over Context
As a general rule of thumb, don't pass objects by Context if it's possible to inject them, because Context objects are type-unsafe.

Only pass objects by Context if they are request-scoped.

Souce: [Context](https://peter.bourgon.org/blog/2016/07/11/context.html) by Peter Bourgon

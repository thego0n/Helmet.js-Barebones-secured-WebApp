# [Introduction to Information Security with HelmetJS Challenges](https://www.freecodecamp.org/learn/information-security/information-security-with-helmetjs/)

https://helmetjs.github.io/

How it works

Helmet is Connect-style middleware, which is compatible with frameworks like Express. (If you need support for Koa, see koa-helmet.)

The top-level helmet function is a wrapper around 15 smaller middlewares, 11 of which are enabled by default.

In other words, these two things are equivalent:

// This...
app.use(helmet());

// ...is equivalent to this:
app.use(helmet.contentSecurityPolicy());
app.use(helmet.dnsPrefetchControl());
app.use(helmet.expectCt());
app.use(helmet.frameguard());
app.use(helmet.hidePoweredBy());
app.use(helmet.hsts());
app.use(helmet.ieNoOpen());
app.use(helmet.noSniff());
app.use(helmet.permittedCrossDomainPolicies());
app.use(helmet.referrerPolicy());
app.use(helmet.xssFilter());

To set custom options for one of the middleware, add options like this:

// This sets custom options for the `referrerPolicy` middleware.
app.use(
  helmet({
    referrerPolicy: { policy: "no-referrer" },
  })
);

You can also disable a middleware:

// This disables the `contentSecurityPolicy` middleware but keeps the rest.
app.use(
  helmet({
    contentSecurityPolicy: false,
  })
);


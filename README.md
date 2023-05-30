# GraphQL Yoga Typescript Help

Hi, I'm new to Typescript, and to GraphQL Yoga. I'm trying to use strict settings for my compiler and linter, and am struggling.

I've created this repo to share this problem. Included in this repo are the strict compiler and linter settings. And the code that reproduces the problem is a copy-paste of [the issues template in the GraphQL Yoga repo](https://github.com/dotansimha/graphql-yoga/blob/c38c6673e0987693a0a1ef4f5f85aed4e71acbac/examples/issue-template/src/main.ts).

## Reproduce the issue

1. Install node 18.
1. Install node packages.
   ```
   yarn
   ```
1. Run the compiler.
   ```
   yarn tsc
   ```

You should see the following error message:
```
src/index.ts:28:29 - error TS2769: No overload matches this call.
  Overload 1 of 2, '(requestListener?: RequestListener<typeof IncomingMessage,
typeof ServerResponse> | undefined): Server<typeof IncomingMessage, typeof Serv
erResponse>', gave the following error.
    Argument of type 'YogaServerInstance<{}, {}>' is not assignable to paramete
r of type 'RequestListener<typeof IncomingMessage, typeof ServerResponse> | und
efined'.
      Type 'YogaServerInstance<{}, {}>' is not assignable to type 'RequestListe
ner<typeof IncomingMessage, typeof ServerResponse>'.
        Types of parameters 'req' and 'req' are incompatible.
          Type 'IncomingMessage' is not assignable to type 'NodeRequest' with '
exactOptionalPropertyTypes: true'. Consider adding 'undefined' to the types of
the target's properties.
            Types of property 'url' are incompatible.
              Type 'string | undefined' is not assignable to type 'string'.
                Type 'undefined' is not assignable to type 'string'.
  Overload 2 of 2, '(options: ServerOptions<typeof IncomingMessage, typeof Serv
erResponse>, requestListener?: RequestListener<typeof IncomingMessage, typeof S
erverResponse> | undefined): Server<...>', gave the following error.
    Type 'YogaServerInstance<{}, {}>' has no properties in common with type 'Se
rverOptions<typeof IncomingMessage, typeof ServerResponse>'.

28 const server = createServer(yoga)
                               ~~~~
```

Any advice how to solve this?

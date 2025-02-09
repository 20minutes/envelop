## `@envelop/apollo-server-errors`

This plugin exposes the same error structure as `apollo-server`. Use this plugin if you are moving to Envelop, and wish to get a compatibility layer for your errors, to make sure the clients receive the same output.

## Getting Started

```
yarn add @envelop/apollo-server-errors
```

## Usage Example

```ts
import { parse, validate, specifiedRules, execute, subscribe } from 'graphql'
import { envelop, useEngine } from '@envelop/core'
import { useApolloServerErrors } from '@envelop/apollo-server-errors'

const getEnveloped = envelop({
  plugins: [
    useEngine({ parse, validate, specifiedRules, execute, subscribe }),
    // ... other plugins ...
    useApolloServerErrors({
      // All fields are optional, and should match what you pass today to ApolloServer
      debug: true, //
      formatError: () => {}
    })
  ]
})
```

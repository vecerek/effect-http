---
title: MockClient.ts
nav_order: 8
parent: Modules
---

## MockClient overview

`Client` implementation derivation for testing purposes.

Added in v1.0.0

---

<h2 class="text-delta">Table of contents</h2>

- [constructors](#constructors)
  - [mockClient](#mockclient)
- [models](#models)
  - [MockClientOptions (type alias)](#mockclientoptions-type-alias)

---

# constructors

## mockClient

Derive mock client implementation from the `Api`

**Signature**

```ts
export declare const mockClient: <A extends Api<Endpoint[]>, H extends Record<string, unknown>>(
  option?: Partial<MockClientOptions<A> & ClientOptions<H>> | undefined
) => (api: A) => Client<A, H>
```

Added in v1.0.0

# models

## MockClientOptions (type alias)

**Signature**

```ts
export type MockClientOptions<A extends Api> = {
  responses: {
    [Id in A['endpoints'][number]['id']]: ClientFunctionResponse<
      Extract<A['endpoints'][number], { id: Id }>['schemas']['response']
    >
  }
}
```

Added in v1.0.0

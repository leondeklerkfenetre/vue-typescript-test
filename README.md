# vue-typescript-test

A repository to demonstrate a type error with embedded components based on a clean new Vue project.
Project initialized with `npm create vue@latest` with typescript, testing, pinia, routing.

The issue to check is in `TestComponent.vue` in the `getTemplate` function where an embedded component is defined via `createApp.component`
With the `methods` block `this` is not scoped to the `data()` block but to just `methods` causing type errors when trying to use data attributes.

You can validate this by running `npm run type-check`

```sh
src/components/TestComponent.vue:25:25 - error TS2339: Property 'msg' does not exist on type '{ getMessage(): string; }'.

25             return this.msg
```

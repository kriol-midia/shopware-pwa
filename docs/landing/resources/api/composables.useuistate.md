<!-- Do not edit this file. It is automatically generated by API Documenter. -->

[Home](./index.md) &gt; [@shopware-pwa/composables](./composables.md) &gt; [useUIState](./composables.useuistate.md)

## useUIState variable

> This API is provided as a preview for developers and may change based on feedback that we receive. Do not use this API in a production environment.
> 

Simple state management for UI purposes.

<b>Signature:</b>

```typescript
useUIState: (rootContext: ApplicationVueContext, stateName?: string | undefined) => {
    isOpen: Readonly<Ref<boolean>>;
    switchState: (to?: boolean | undefined) => void;
}
```

## Remarks

If you pase `stateName` on composable invocation (ex. `useUIState(root, 'sidebarCart')`<!-- -->), then state is shared between all instances with this key. Otherwise state is local, so multiple `useUIState(root)` will not share state

## Example


```ts
// Component1
const {isOpen, switchState} = useUIState(root, 'SIDEBAR_STATE')
switchState()

// Component 2
const {isOpen} = useUIState(root, 'SIDEBAR_STATE')
// isOpen will be true

```
If you'll not use KEY on composable init, then state is only local

```ts
// Component1
const {isOpen, switchState} = useUIState(root)
switchState()

// Component 2
const {isOpen} = useUIState(root)
// isOpen will be false

```

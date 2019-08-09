## Component
```dart
Component(@required ViewBuilder<T> view, Reducer<T> reducer, ReducerFilter<T> filter,
        Effect<T> effect, Dependencies<T> dependencies, ShouldUpdate<T> shouldUpdate, 
        WidgetWrapper wrapper, Key Function(T) key)
```

```dart
ComponentContext createContext(
        Store<Object> store,
        BuildContext buildContext, 
        Get<T> getState, 
        { @required void Function() markNeedsBuild, 
        @required DispatchBus bus,
        @required Enhancer<Object> enhancer,
        }){
    return ComponentContext<T>(
            logic: this,
            store: store,
            buildContext: buildContext,
            getState: getState,
            view: enhancer.viewEnhance(protectedView, this, store),
            shouldUpdate: protectedShouldUpdate,
            name: name,
            markNeedsBuild: markNeedsBuild,
            sidecarCtx: adapterDep()?.createContext(
                store,
                buildContext,
                getState,
                bus: bus,
                enhancer: enhancer,
                ),
            enhancer: enhancer,
            bus: bus
            )
}
```

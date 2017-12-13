# babel-plugin-vue-jsx-sync
> jsx plugin for vue sync [sync modifier](https://vuejs.org/v2/guide/components.html#sync-Modifier), inspired by [babel-plugin-jsx-v-model](https://github.com/nickmessing/babel-plugin-jsx-v-model)

# Usage
```
function a() {
  return (
    <div>
      <component visible$sync={this.test}>I am newbie</component>
    </div>
  )
}
```

is complied to:

```
function a() {
  return h(
    "div",
    null,
    [h(
      "component",
      {
        attrs: { visible: this.test },
        on: {
          "visible:update": $$val => {
            this.visible = $$val;
          }
        }
      },
      ["I am newbie"]
    )]
  );
}
```

# dev

```
npm install -g parcel-bundler
npm install
npm run dev
```
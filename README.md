# vue-sticky-directive

vue-sticky-directive is a powerful vue directive make element sticky.

# Install

```Bash
npm install vue-sticky-directive --save
```

ES2015
```JavaScript
// register globally
import Sticky from 'vue-sticky-directive'
Vue.use(Sticky)

// or for a single instance
import Sticky from 'vue-sticky-directive'
new Vue({
  directives: {Sticky}
})
```

# Usage

Use `v-sticky` directive to enable element postion sticky, and use `sticky-*` attributes to define its options. Sticky element will find its nearest element with `sticky-container` attribute or its parent node if faild as the releative element.

[basic example](https://mehwww.github.io/vue-sticky-directive/examples/basic/)

```HTML
<div sticky-container>
  <div v-sticky sticky-offset="offset" sticky-side="top">
    ...
  </div>
</div>
```

# Options
* `sticky-offset` - set sticky offset, it support a vm variable name or a js expression like `{top: 10, bottom: 20}`
  * `top`_(number)_ - set the top breakpoint (default: `0`)
  * `bottom`_(number)_ - set the bottom breakpoint (default: `0`)
* `sticky-side`_(string)_ - decide which side should be sticky, you can set `top`、`bottom` or `both` (default: `top`)
* `sticky-z-index` _(number)_ - to set the z-index of element to stick
* `sticky-id` _(number)_
* `on-stick` _(function)_ - callback when sticky and release, receiveing 1 argument with object indicating the state, like:

```javascript
// The element is sticked on top
{
  bottom: false,
  top: true,
  sticked: true
}
```

An expression that evaluates to false set on `v-sticky` can be used to disable stickiness condtionally.

```HTML
<div sticky-container-5>
  <div v-sticky="shouldStick" sticky-id="5">
    ...
  </div>
</div>
```
```JavaScript
export defaults {
  data () {
    shouldStick: false
  }
}
```

# License

MIT



<div align="center">
  <img src="https://raw.githubusercontent.com/VueServerRenderer/VueServerRenderer/main/lzyaemujz884m4tggslk.webp" width="200" alt="logo"/>
</div>

## Deno vue-template-compiler

This is a port of the [vue-template-compiler](https://github.com/vuejs/vue/tree/dev/packages/vue-template-compiler) from the [vuejs](https://github.com/vuejs/vue)    repo.

This only contains the `build.js` file along with its dependencies.

## Usage

In contrast to the original vue-template-compiler, each function is being exported instead of a single object. You can directly reference only the methods needed.

Example:
```typescript
import { parseComponent } from 'https://deno.land/x/vue_template_compiler@1.0.0/mod.js';

const template = await Deno.readTextFile(Deno.cwd() + '/App.vue');
const parsed = parseComponent(template);
console.log(parsed);
```

Output:
```
{
  template: {
    type: "template",
    content: '\n<div id="app">\n  <img\n    src="https://svgshare.com/i/SNz.svg"\n    alt="image"\n    border="0"\n    w...',
    start: 10,
    attrs: {},
    end: 218
  },
  script: {
    type: "script",
    content: "\nimport what from './components/what.vue';\n\nexport default {\n  name: 'app',\n  components: {what},\n};...",
    start: 239,
    attrs: {},
    end: 341
  },
  styles: [
    {
      type: "style",
      content: "\nhtml {\n  background-color: #203A42;\n}\n#app {\n  font-family: Avenir, Helvetica, Arial, sans-serif;\n ...",
      start: 359,
      attrs: {},
      end: 597
    }
  ],
  customBlocks: [],
  errors: []
}

```

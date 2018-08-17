# vs-tags

This is Tags Input Component created by VueJS

## Getting Started

These instructions will get you a copy of the component up and running on your local machine.

### Installing

You can install vs-tags component by npm

```
npm i vs-tags
```

After download, vs-tags will be ready to use in your VueJS Applications

### Usage

* Just import Components from node_modules folder in main.js

```
import Tags from "vs-tags"
```

* Register vs-tags component with any name you want

```
Vue.component("vtag", Tags);
```

After this step, vs-tags can be used by all registered component in your project with vtag tag name 

* You can use with <vtag></vtag>

```
<vtag></vtag>
```

#### Styling

vs-tags has 6 color options

* primary
* secondary
* success
* danger
* info
* warning

To use these colors, just add 'color' attribute into vtag component

```
<vtag color="primary"></vtag>
```

```
<vtag color="secondary"></vtag>
```

```
<vtag color="success"></vtag>
```

```
<vtag color="danger"></vtag>
```

```
<vtag color="info"></vtag>
```

```
<vtag color="warning"></vtag>
```

#### Data Binding

Also you can bind vs-tags component by v-model VueJS directive

```
<vtag v-model="tags"></vtag>
```

This data property will give us all tags with comma seperator.

```
kablosuzkedi,vuejs,videosinif,inputtag
```

## Versioning

We use [GitHub](https://github.com/gkandemi/vue-tag) for versioning. For the versions available, see the [tags on this repository](https://github.com/gkandemi/vue-tag/tags). 

## Authors

* **Gökhan Kandemir** - [Gökhan Kandemir](https://github.com/gkandemi)

## License

This project is licensed under the MIT License


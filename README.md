# filter

<!-- [![NPM version](https://img.shields.io/npm/v/@opengis/filter?style=plain)](https://www.npmjs.com/package/@opengis/filter) -->

A flexible and extensible filter component system for Vue 3.
Ideal for building customizable filter UIs with checkbox, radio, or custom slot fields.

## Features

- Schema-based filter rendering (radio, checkbox)
- Layouts (vertical, inline, popover)
- Slot-based extensibility for custom filters
- Built-in clear/reset support
- Emits `change` and `clear` events
- Popover support with positioning logic
- Show more / limit options logic
- Written in TypeScript
- Fully styleable with Tailwind CSS
- Mobile-friendly and responsive

## Documentation

Complete documentation and examples available at [https://filter.opengis.info](https://filter.opengis.info)

- [Component documentation](https://filter.opengis.info/guide/)

## Changelog

Full change log available at [https://filter.opengis.info/changelog/](https://filter.opengis.info/changelog/)

## Install & Usage

### 1. Install the package
```bash
npm i @opengis/filter
```
### 2. Register the component
```typescript
// main.ts or main.js
import { createApp } from 'vue'
import App from './App.vue'
import InlineFilter from '@opengis/filter'

createApp(App).component('Filter', InlineFilter).mount('#app')
```
### 3. Use it in your template

```vue

<template>
  <filter :schema="schema" @change="filter = $event" @clear="console.log($event.data)">
    <filter-field :options="options" label="test label" limit=1 name="test" type="checkbox"/>
  </filter>
</template>

<script setup lang="ts">
  import {ref} from 'vue'
  import {ListItem, Schema} from "./forms.model";

  const options: ListItem[] = [
    {
      value: 'is_video',
      label: 'Відео',
    },
    {
      value: 'is_photo',
      label: 'Фото',
    },
  ];

  const schema = ref({
    name: {type: 'radio', label: 'Наявність фото / відео', options}
  } as Schema);

  const selectedIcon = ref('')
  const myIcons = ['home', 'user', 'settings', 'arrow-left', 'check'] // your SVG names
</script>
```

## Contributions

We welcome contributions!
Feel free to open issues, suggest features, or submit pull requests.

## Licence

MIT

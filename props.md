## Parent.vue
```
<template>
    <div>
        <h1>Parent</h1>
        <Child :title="message" :age="age" :arr="arr" :objectarr="objectarr" />
    </div>
</template>

<script setup lang="ts">
import Child from './Child.vue'
const message = ref('Parent数据')
const age = ref(18)
const arr = ref(["iwen", "ime", "frank"])
const objectarr = ref([{ name: "iwen", age: 18 }, { name: "ime", age: 19 }, { name: "frank", age: 20 }])
</script>


<style scoped></style>
```
## Child.vue
```
<template>
    <div>
        <h1>Child</h1>
        <p>{{ title }}</p>
        <p>{{ age }}</p>
        <ul>
            <li v-for="value in arr" :key="value">{{ value }}</li>
        </ul>
        <p v-for="(key, index) in objectarr" :key=index>{{ key.name }}-{{ key.age }}</p>

    </div>
</template>
<script setup lang="ts">
const props = defineProps({
    title: String,
    age: Number,
    arr: Array,
    objectarr: Object
})
</script>
<style scoped></style>
```


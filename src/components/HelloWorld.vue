<template>
  <div class="about">
    <h1 ref="elm">This is an composition api test page</h1>
    <h2>ref</h2>
    <h2>{{ count }}</h2>
    <h2>cumputed</h2>
    <h2>{{ com }}</h2>
    <button @click="increment">click to +</button>
    <button @click="decrement">click to -</button>

    <h2>reactive</h2>
    <h2>{{ count2.a }}</h2>
    <button @click="re">click to plus</button>
    <button @click="de">click to minus</button>

    <h2>mounted</h2>
    <h3>{{ number }}</h3>

    <h2>prop</h2>
    <h3>{{ prop }}</h3>

    <button @click="onClick">押す</button>
  </div>
</template>

<script setup>
import { ref, reactive, computed, onMounted, defineProps, defineEmits, watch } from 'vue'

// const prop = ref()
const number = ref(1)
const count = ref(0)
// const watche = ref(5)
const count2 = reactive({ a: 0, b: 0 })
const increment = () => count.value++
const decrement = () => count.value--
const re = () => count2.a++
const de = () => count2.a--

const com = computed(() => count.value * 2)
onMounted(() => { number.value = 10 })

const prop = defineProps(['propa'])

// const click = ref('hi')
const emit = defineEmits(['click'])
const onClick = () => { emit('click') }

watch(count, (cr, prev) => {
  console.log(cr, prev)
})

const elm = ref(null)
onMounted(() => { console.log(elm.value) })
</script>

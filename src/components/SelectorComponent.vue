<template>
    <h1>{{ label }}</h1>
    <NButton>Ashiq</NButton>
    <NDatePicker />
</template>
<script>
import { NButton, NDatePicker } from 'naive-ui'
export default {
    props: {
        label: String
    },
    components: {
        NButton,
        NDatePicker
    }
}
</script>
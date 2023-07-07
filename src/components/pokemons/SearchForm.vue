<script>
export default {
    data() {
        return {
            selectedOption: ''
        }
    },
    props: {
        options: Array,
        defaultLabel: String,
    },
    emits: ['option-change']
}
</script>

<template>
    <select class="form-select mb-3" v-model="selectedOption" @change="$emit('option-change', selectedOption)">
        <option selected> {{ defaultLabel || '---' }} </option>
        <option v-for="option in options" :key="option"> {{ option }}</option>
    </select>
</template>

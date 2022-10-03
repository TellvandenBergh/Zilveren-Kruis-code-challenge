<template>
    <div class="form-input my-4">
        <div class="input__group">
            <label class="input__title">{{ label }}</label>
            <input
                @input="handleInput"
                class="input__field form-control"
                :class="isValid == false && 'is-invalid'"
                :type="type ? type : 'text'"
            />
        </div>
        <div
            v-if="isValid == false"
            class="input__feedback invalid-feedback mt-1"
            aria-live="polite"
        >
            <span>{{ errorMessage }}</span>
        </div>
    </div>
</template>

<script>
export default {
    props: ['label', 'type', 'isValid', 'errorMessage'],
    methods: {
        handleInput(e) {
            this.$emit('input', e.target.value);
        }
    }
};
</script>

<style lang="scss" scoped></style>

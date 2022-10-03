<template>
    <div class="form-input my-4">
        <div class="input__group">
            <label class="input__title">{{ title }}</label>
            <div class="form-row">
                <div
                    v-for="(option, index) in options"
                    class="radio custom-radio radio__option"
                    :key="index"
                >
                    <input
                        @input="handleInput"
                        :id="option"
                        class="radio__input custom-control-input"
                        type="radio"
                        name="geslacht"
                    />
                    <label
                        class="radio__label custom-control-label"
                        :for="option"
                    >
                        {{ option }}
                    </label>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    props: ['title', 'options'],
    methods: {
        handleInput(e) {
            console.log(e.target.id);
            this.$emit('input', e.target.id);
        }
    }
};
</script>

<style lang="scss" scoped></style>

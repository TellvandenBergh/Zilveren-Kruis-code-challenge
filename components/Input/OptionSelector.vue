<template>
    <div class="form-input my-4">
        <label class="input__title">
            {{ title }}
        </label>
        <div class="input__group">
            <select class="form-control">
                <option v-for="(option, index) in options" :key="index">
                    {{ option }}
                </option>
            </select>
        </div>
    </div>
</template>

<script>
export default {
    props: ['title', 'options']
};
</script>

<style lang="scss" scoped></style>

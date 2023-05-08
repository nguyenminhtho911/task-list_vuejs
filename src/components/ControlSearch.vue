<template>
    <div class="col-12">
        <div class="input-group">
            <input 
                v-bind:value="strSearch"
                v-on:input="handleSearch"
                type="text" class="form-control" placeholder="Search for..." />
            <span class="input-group-append">
                <button 
                    v-on:click="handleClear"
                    class="btn btn-info" type="button">Clear!</button>
            </span>
        </div>
    </div>
</template>

<script>
// v-model => v-bind -> v-on:input
export default {
    name: 'control-search',
    props: {
        strSearch: { type: String, default: '' }
    },
    data() {
        return { }
    },
    methods: {
        handleClear() {
            // Thay đổi giá trị strSearch về ''
            this.$emit('handleSearch', '');
        },
        handleSearch(e) {
            this.$emit('handleSearch', e.target.value);
        }
    }
}
</script>

<style>

</style>

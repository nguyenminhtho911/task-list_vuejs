<template>
    <div class="col-12">
        <div class="form-group">
            <b-dropdown text="Sort by">
                <b-dropdown-item v-on:click="handleSort('name', 'asc')">Name ASC</b-dropdown-item>
                <b-dropdown-item v-on:click="handleSort('name', 'desc')">Name DESC</b-dropdown-item>
                <b-dropdown-divider />
                <b-dropdown-item v-on:click="handleSort('level', 'asc')">Level ASC</b-dropdown-item>
                <b-dropdown-item v-on:click="handleSort('level', 'desc')">Level DESC</b-dropdown-item>
            </b-dropdown>
            <span class="order badge badge-success badge-medium">{{ orderBy }} - {{ orderDir }}</span>
        </div>
    </div>
</template>

<script>
export default {
    name: 'control-sort',
    props: {
        orderBy: { type: String, default: 'name' },
        orderDir: { type: String, default: 'asc' },
    },
    data() {
        return { }
    },
    methods: {
        handleSort(orderBy, orderDir) {
            let data = { orderBy, orderDir }
            this.$emit('handleSort', data);
        }
    }
}
</script>

<style>
    .order {
        text-transform: uppercase;
    }
</style>

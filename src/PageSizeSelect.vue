<template>
    <span>records of {{total}} total records -
        <label name="PageSizeSelect">
            <select class="form-control input-sm -page-size-select" v-model="query.limit"
                    @change="query.offset = 0 /* reset to the first page */">
                <option v-for="i in pageSizeOptions" :value="i">{{ i }}</option>
            </select>
            per page
        </label>
    </span>
</template>
<script>
    export default {
        name: 'PageSizeSelect',
        props: {
            query: {type: Object, required: true},
            pageSizeOptions: {type: Array, required: true},
            total: {type: Number, required: true}
        },
        created() {
        }
    }
</script>
<style>
    .-page-size-select {
        display: inline-block;
        width: 65px;
    }
</style>

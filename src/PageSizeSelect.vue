<template>

        <div class="col-sm-6" style="white-space: nowrap">
        {{this.query.limit * currentPage}} records of {{total}} total records -
        <label name="PageSizeSelect">
            <select class="form-control input-sm -page-size-select" v-model="query.limit"
                    @change="query.offset = 0 /* reset to the first page */">
                <option v-for="i in pageSizeOptions" :value="i">{{ i }}</option>
            </select>
            {{ $i18nForDatatable('items / page') }}
        </label>
        </div>
</template>
<script>
    export default {
        name: 'PageSizeSelect',
        props: {
            query: {type: Object, required: true},
            pageSizeOptions: {type: Array, required: true},
            total: 0,
            currentPage:1,
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

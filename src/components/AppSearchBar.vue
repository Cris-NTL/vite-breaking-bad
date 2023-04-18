<script>
export default {
    name: 'SearchBar',
    emits: ['filter'],
    data() {
        return {
            statusOptions: ['Alien', 'Ally of Justice', 'Ancient Gear'],
            selectedStatus: '',
        };
    },
};
</script>

<template>
    <div class="container my-3">
        <div class="d-flex justify-content-end">
            <select class="form-select w-25" name="status" id="status" v-model="selectedStatus"
                @change="() => $emit('filter', selectedStatus)">
                <option value="">All</option>
                <option :value="status" v-for="status in statusOptions">{{ status }}</option>
            </select>
        </div>
    </div>
</template>

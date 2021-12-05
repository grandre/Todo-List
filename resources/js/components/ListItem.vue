<template>
    <div>
        <div v-for="(item, index) in items" :key="index">
            <items
                :item="item"
                class="item"
                v-on:itemchanged="$emit('reloadlist')"
                v-on:itemdestroyed="$emit('reloadlist')"
            />
        </div>
    </div>
</template>

<script>
export default {
    props: ["items"],
};
</script>

<style scoped>
.item {
    background: #e6e6e6e6;
    padding: 5px;
    margin-top: 5px;
}
</style>

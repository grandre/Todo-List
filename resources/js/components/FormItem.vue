<template>
    <div class="addItem">
        <input type="text" v-model="item.name" />
        <font-awesome-icon
            icon="plus"
            @click="addItem()"
            :class="[item.name ? 'active' : 'inactive', 'plus']"
        />
    </div>
</template>

<script>
export default {
    data: function () {
        return {
            item: {
                name: "",
            },
        };
    },
    methods: {
        addItem() {
            if (this.item.name == "") {
                return;
            }

            axios
                .post("api/item/store", {
                    item: this.item,
                })
                .then((response) => {
                    if (response.status == 201) {
                        this.item.name = "";
                        this.$emit("reloadlist");
                    }
                })
                .catch((error) => {
                    console.log(error);
                });
        },
    },
};
</script>


<style scoped>
.addItem {
    display: flex;
    flex-direction: row;
    justify-content: center;
}
input {
    background: #f7f7f7f7;
    border: 0px;
    outline: none;
    margin-right: 10px;
    width: 100%;
    font-size: 20px;
}
.plus {
    font-size: 40px;
}
.active {
    color: #00c71b;
}
.inactive {
    color: #999999;
}
</style>
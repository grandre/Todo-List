<template>
    <div class="container">
        <div class="card">
            <div class="header">
                <h2 class="title">Lista de afazeres</h2>
                <form-item 
                    v-on:reloadlist="getList()"></form-item>
            </div>
            <div class="list">
                <list-item
                    :items="items"
                    v-on:reloadlist="getList()"
                ></list-item>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    data: function () {
        return {
            items: [],
        };
    },
    methods: {
        getList() {
            axios
                .get("api/items")
                .then((response) => {
                    this.items = response.data;
                })
                .catch((error) => {
                    console.log(error);
                });
        },
    },
    created() {
        this.getList();
    },
};
</script>

<style scoped>
.container {
    display: flex;
    flex-direction: row;
    justify-content: center;
}

.card {
    border-radius: 5px;
    box-shadow: 7px 7px 13px 0px rgba(50, 50, 50, 0.22);
    padding: 30px;
    margin: 20px;
    width: 400px;
    transition: all 0.3s ease-out;
}

.card p {
    color: #a3a5ae;
    font-size: 16px;
}

.card:hover {
    box-shadow: 0 8px 16px 0 rgba(0, 0, 0, 0.2);
}

.header {
    background: #ebebeb;
    padding: 5px;
    margin-top: 5px;
    border-left: 10px solid #0096ff;
}
</style>


<template>
    <div>
        <p>{{label}}</p>
        <div class="form-group"
            v-for="item in items"
            :key="item.key">
            <input type="text"
            :placeholder="placeholder"
            v-model="item.description"
            :tabindex="setTabIndex(item)">
            <button v-on:click="addItem()">+</button>
            <button v-on:click="removeItem(item)">-</button>
        </div>
    </div>
</template>

<script>
export default {
    name: 'InputMultiple',
    props: [
        'placeholder',
        'label',
        'name'
    ],
    data: function() {
        return {
            items: [
                {
                    key: this.generateKey()
                }
            ]
        }
    },
    methods: {
        addItem: function() {
            let newKey = this.generateKey();
            this.items.push({key: newKey, description: this.description});
        },
        removeItem: function(item) {
            const index = this.items.map(function(object) {return object.key}).indexOf(item.key);
            this.items.splice(index, 1);
        },
        setTabIndex: function(item) {
            let index = this.items.map(function(object) {return object.key}).indexOf(item.key);
            return index += 1;
        },
        generateKey: function() {
            return Math.floor(Math.random() * Math.floor(10000000));
        },
    }
    
}
</script>

<style scoped>

</style>



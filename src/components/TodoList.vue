<template>
    <div class="todo-list">
        <input type="text" placeholder="Press Enter to save ..." v-model="newItem.task" v-on:keyup.enter="saveItem">
        <table>
            <tr v-for="item in items">
                <td>{{ item.date }}</td>
                <td>{{ item.task}}</td>
                <td><button v-on:click="removeItem(item)">-</button></td>
            </tr>
        </table>
    </div>
</template>

<script>
export default {
    name: 'todo-list',
    data () {
        return {
            newItem : {},
            items : [
                {
                    date: '10/11/2018',
                    task: 'study web development'
                },
                {
                    date: '10/11/2018',
                    task: 'read'
                },
            ],
        }
    },
    methods: {
        saveItem: function(){
            this.newItem.date = this.getDate;
            this.items.push(this.newItem);
            this.newItem = {};
        },
        removeItem: function(item){
            this.items.splice(this.items.indexOf(item), 1);
        }
    },
    computed: {
        getDate: function(){
            var date = new Date();
            var month = date.getMonth() + 1;
            var year = date.getFullYear();
            var date = date.getDate();
            return month + '/' + date + '/' + year;
        }
    }

}
</script>

<style scope>
   table {
       margin:auto;
       width: 75%;
   }

   table tr {
       border: 1px solid black;
       border-radius: 5px;
       padding:10px;
   }

   table tr td:nth-child(2) { 
       width:100%;
    }

    input {
        width: 75%;
        padding:10px;
        margin: 20px 20px;
        border-radius: 5px;
        border-color: #4ac08e;
        
    }
</style>


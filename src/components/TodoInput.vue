<template>
    <div class="inputBox shadow">
        <input type="text" v-model="newTodoItem" v-on:keyup.enter="addTodo">
        <span class="addContainer" v-on:click="addTodo">
            <i class="fas fa-plue addBtn"></i>
        </span>
        <Modal v-if="showModal" @close="showModal=false">
        </Modal>
    </div>
</template>
<script>

import Modal from './common/Modal.vue'
export default {
    data : function() {
        return {
            showModal : false
        }
    },
    methods : {
        addTodo : function() {
            if(this.newTodoItem !== '') {
                //var obj = {completed : false, item : this.newTodoItem};
                //localStorage.setItem(this.newTodoItem, JSON.stringify(obj));
                this.$emit('addItemEvent', this.newTodoItem);
                this.clearInput();
            } else {
                console.log("데이터없음");
                this.showModal = !this.showModal;
                console.log(this.showModal);
            }
        },
        clearInput : function() {
            this.newTodoItem = '';
        }
    }, 
    components : {
        'Modal' : Modal
    }
}
</script>
<style scoped>
 input:focus { outline: none; } 
 .inputBox { background: white; height: 50px; line-height: 50px; border-radius: 5px; } .inputBox input { border-style: none; font-size: 0.9rem; } 
.addContainer { float: right; background: linear-gradient(to right, #6478FB, #8763FB); display: block; width: 3rem; border-radius: 0 5px 5px 0; } 
.addBtn { color: white; vertical-align: middle; } 
.closeModalBtn { color: #42b983; } 
</style>
<script>
        export default {
                props :[
                        'state'
                ],
                methods : {
                        removeTodo(itemId) {
                                this.state.list = this.state.list.filter(item => item.id !== itemId)
                        },
                        toggleFinish(itemId){
                                this.state.list = this.state.list.map(item => item.id === itemId ? {...item,finished : !item.finished} : item)
                        }
                } 
        }
</script>

<template>
        <div class="list">
                <div class="list-item" v-for="item in state.list">
                        <div class="body-item-list">
                                <div :class="item.finished ? 'todo-finished content' : 'content'">{{ item.content }}</div>
                                <div class="tools-list-item">
                                        <button class="todo-checkbox" @click="toggleFinish(item.id)">
                                                <svg v-show="item.finished" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" strokeWidth={1.5} stroke="currentColor" className="size-6">
                                                        <path strokeLinecap="round" strokeLinejoin="round" d="m4.5 12.75 6 6 9-13.5" />
                                                </svg>
                                        </button>
                                        <button class="btn-trash" @click="removeTodo(item.id)">
                                                <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="">
                                                        <path stroke-linecap="round" stroke-linejoin="round" d="m14.74 9-.346 9m-4.788 0L9.26 9m9.968-3.21c.342.052.682.107 1.022.166m-1.022-.165L18.16 19.673a2.25 2.25 0 0 1-2.244 2.077H8.084a2.25 2.25 0 0 1-2.244-2.077L4.772 5.79m14.456 0a48.108 48.108 0 0 0-3.478-.397m-12 .562c.34-.059.68-.114 1.022-.165m0 0a48.11 48.11 0 0 1 3.478-.397m7.5 0v-.916c0-1.18-.91-2.164-2.09-2.201a51.964 51.964 0 0 0-3.32 0c-1.18.037-2.09 1.022-2.09 2.201v.916m7.5 0a48.667 48.667 0 0 0-7.5 0" />
                                                </svg>
                                        </button>
                                </div>
                        </div>
                </div>
        </div>
</template>

<style scoped>

</style>
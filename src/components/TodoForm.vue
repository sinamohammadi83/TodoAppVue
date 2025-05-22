<script>
        


        export default {
                data(){
                        return {
                                content : ''
                        }
                },
                props :[
                        'state'
                ],
                methods : {
                        saveTodo() {                                                                
                               this.state.list = [...this.state.list, { id : this.state.list.length+1, content : this.content, finished : false }]
                               this.content = ''
                               this.$emit('updateList',this.state.list)
                        }
                }
        }

        
        
</script>

<template>
        <div class="section-todo">
                <div class="box-to-do">
                        <div class="header">Todo List</div>
                        <div class="todo-body">
                                <div>
                                        <label for="" class="label-title">
                                                content 
                                        </label>
                                        <textarea v-model="content" type="text" class="inp-title"></textarea>
                                </div>
                                <div class="box-btn-todo">
                                        <button class="btn-submit-todo" @click="saveTodo()">
                                                save
                                        </button>
                                </div>
                        </div>
                </div>
        </div>
</template>

<style scoped>

</style>
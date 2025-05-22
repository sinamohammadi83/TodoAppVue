<script>
        


        export default {
                data(){
                        return {
                                content : '',
                                contentError : false
                        }
                },
                props :[
                        'state'
                ],
                methods : {
                        saveTodo() {      
                                this.contentError = false;
                                if(this.content.length > 0)  {                                                        
                                        this.state.list = [...this.state.list, { id : this.state.list.length+1, content : this.content, finished : false }]
                                        this.content = ''
                                        this.$emit('updateList',this.state.list)
                                }else{
                                        this.contentError = true
                                }
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
                                        <div>
                                                <span class="content-erorr" v-show="contentError">The content field has required.</span>
                                        </div>
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
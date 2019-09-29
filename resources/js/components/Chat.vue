<template>
    <div class="container">
        <div class="row justify-content-center mt-3">
            <div class="col-md-6">
             <li class="list-group-item active text-center">Chat App</li>
            <ul class="list-group" v-chat-scroll >
            <div v-for="value in chat.message" :key="value.index">
             <li class="list-group-item list-group-item-success text-success" >{{ value }}
             </li>
             <small class="badge float-right badge-success">You</small>
            </div>

            </ul>
            <div class="form-group">
              <input type="text" class="form-control" placeholder="Type here..." name="message" v-model="message" @keyup.enter="save">
            </div>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        data(){
            return{
                message:'',
                chat:{
                    message:[]
                },

            }

        },

        mounted() {
            console.log('Component mounted.')
        },
        methods:{
            save(){
                if(this.message.length!=0)
                {
                    this.chat.message.push(this.message)
                    this.message=''

                }

            }
        }

    }
</script>
<style scoped>
.list-group{
    overflow-y: scroll;
    height: 200px;
}
</style>

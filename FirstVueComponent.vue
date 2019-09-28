<template>
    <div class="card">
        <div class="card-header">First Vue Component Ever</div>

        <div class="card-body">
            <div class="form-group">
                <label for="exampleInputEmail1">Reverse Copier and Talk sensetive</label>
                <input type="email" class="form-control" id="exampleInputEmail1" v-on:input="changeTitle">
                <small id="emailHelp" class="form-text text-muted">{{ title }}</small>
                <small id="emailHelp" class="form-text text-muted" v-if="talkative">STOP TALKING</small>
                <small id="emailHelp" class="form-text text-muted" v-if="!talkative">I dare you to talk</small>
                <hr>
                <label for="exampleInputEmail1">Link Spoofer</label>
                <input type="email" class="form-control" id="exampleInputEmail1" v-model="link">
                <a v-bind:href="link">click on the link</a>

            </div>
        </div>
    </div>
</template>

<script>
    export default {
        data: function(){
            return {
                title: "",
                link: "http://google.com"
            }
        },
        computed:{
            talkative: function(){
                if(this.title.length > 10){
                    return true;
                }else{
                    return false;
                }
            }
        },
        methods:{
            changeTitle: function(){
                this.title = event.target.value.split("").reverse().join("");
            }
        }
    }
</script>

<template>
    <div class="backdrop" @click.self="closechild">
        <div class="modal">
            <h1>{{ header }}</h1>
            <h1>{{ footer }}</h1>
            <slot></slot>
            <div>
                <slot name="links"></slot><hr><hr>
            </div>
            

            
            
            <p>------ Child Components -----</p>

        </div> 
    </div>
</template>
<script>
export default {
    props:['header' ,'footer'],
    methods:{
         closechild(){
           this.$emit('close')

    }

   

    }
}
</script>


<style>
.modal{
    width:400px;
    padding: 20px;
    margin: 100px auto;
    background: white;
    border-radius: 10px;
}
.backdrop{
    top: 0;
    position: fixed;
    background: rgb(0, 0, 0 ,.5);
    width: 100%;
    height: 100%;
}

</style>
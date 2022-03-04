<template>
    <div class="backdrop" @click.self="closeModal">
        <div class="modal" :class="{sale: theme==='sale'}">
            <h1>{{header}}</h1>
            <p>{{text}}</p>
            <slot></slot>
            <div class="actions">
                 <slot name="link"></slot>
            </div>
        </div>

        
    </div>
</template>



<script>


export default ({
    // name :Modal
    props:['header','text','theme'],
    methods:{
        closeModal(){
            this.$emit('close')
            
        }
    }
   
    
})
</script>

<style>

 
.modal{
    width:400px;
    padding:20px;
    margin:100px auto;
    background-color:white;
    border-radius:10px;
}
.backdrop{
    top:0;
    position:fixed;
    background-color:rgba(0, 0, 0, 0.5);
    width:100%;
    height:100%;
}
h1 { 
    /* color:rgb(96, 236, 96); */
    border:none;
    padding:0;
}
.modal.sale{
    background-color:rgb(139, 86, 99);
    color:white;

}
.modal.sale h1{
    color:white;

}

.modal .actions  {
    text-align: center;
    margin: 30px 0 10px 0;
    
}
.modal .actions  a {
    color: white;
    padding: 10px 20px;
    border: 1px solid white;
    text-decoration: none;
    margin: 10px ;



}
.modal.sal .actions{
    color:white;
}
.modal.sal .actions a {
    color: white;
}




</style>
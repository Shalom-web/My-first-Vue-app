<template>
    <div class="backdrop" @click.self="closeModal">
        <div class="modal" :class="{sale: theme === 'sale'}"> 
          <slot>Dafault Contents</slot>
          <div class="actions">
            <slot name="links"></slot>
          </div>
        </div>
    </div>
</template>

<script>
    export default{
        props: ['theme'],
        methods: {
            closeModal(){
                this.$emit('close')
            }
        }
    }
</script>

<style>
    .modal{
        width: 500px;
        padding: 20px;
        margin: 100px auto;
        background: white;
        border-radius: 10px;
        text-align: center;
    }
    .backdrop{
        top: 150px;
        position: fixed;
        background: rgb(227, 223, 223);
        width: 100%;
        height: 100%;
       
    }
    .modal h1{
        color: rgb(0, 0, 0);
        border: none;
        padding: 0;
        font-weight: 700;
    }
    .modal p{
        font-style: normal;
    }
    .modal .actions{
        text-align: center;
        margin: 30px 0 10px 0;
        color: #333;
    }
    .modal .actions a{
        color: #333;
        padding: 8px;
        border: 1px solid #eee;
        border-radius: 4px;
        margin: 10px;
    }
    .modal.sale{
        background: rgb(85, 188, 239);
        color: rgb(255, 255, 255);
    }
    .modal.sale.h1{
        color: white;
    }
    .modal.sale .actions a{
        color: white;
    }
</style>
<template>
    
    <div class="backdrop" @click.self="closeModal">
        <div class="modal" :class="{ custom:theme === 'custom' }">
            <slot></slot>
            <div class="actions">
                <slot name="links"></slot>
                <slot name="test"></slot>
            </div>
        </div>
    </div>
    
</template>

<script>
export default{
    props: ['theme'],
    methods:{
        closeModal(){
            this.$emit('close')
        }
        }
    }
</script>

<style>
    .modal{
        width: 400px;
        padding: 20px;
        margin: 100px auto;
        background: white;
        border-radius: 10px;
    }
    .backdrop{
        top: 0;
        position: fixed;
        background: rgba(0,0,0,0.5);
        width: 100%;
        height: 100%;
    }
    .modal h1{
        color: #03cfb4;
        border: none;
        padding: 0;
    }
    .modal p{
        font-style: normal;
    }
    .modal .actions{
        text-align: center;
        margin: 30px 0 10px 0;
    }
    .modal .actions a{
        color: #333;
        padding: 8px;
        border: 1px solid purple;
        border-radius: 4px;
        text-decoration: none;
        margin: 10px;
    }
    .modal.custom {
        background: bisque;
        color: blueviolet;
    }
    .modal.custom h1{
        color: purple;
    }
    .modal.custom .actions{
        color: blueviolet;
    }
    .modal.custom .actions a{
        color: purple;
    }
</style>
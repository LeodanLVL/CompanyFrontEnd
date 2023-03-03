

<template>
    <div class="overlay">

        <div class="formulario">
            
            
            <div class="container-formulario">
                
                <div class="input">
                    <p>Name:</p>
                    <input type="text" name="name">
                </div>
                <div class="input">
                    <p>Email:</p>
                    <input type="text" name="email">
                </div>
                <div class="input">
                    <p>Phone:</p>
                    <input type="text" name="phone">
                </div>
                <div class="input">
                    <p>Provider:</p>
                    <input type="text" name="provider">
                    <button>insert</button>
                </div>
                <button @click="close">Cancelar</button>
                <button>Insert client</button>
                <!-- <div class="input"></div> -->
            </div>
            
        </div>
    </div>
    </template>

<script>
    export default{
        name: 'FormClient',
        methods:{
            close(){this.$emit('close')}
        }
    }
</script>

<style scoped>
.overlay {
    position: absolute;
    width: 100%;
    height: 100%;
    background-color: rgb(0, 0, 0, 0.77);
    z-index: 10;
    display: flex;
  justify-content: center;
  align-items: center;
}
div .formulario{
    border-radius: 10px;
    background-color: white;
    width: 70%;
    height: 70%;
    display: flex;
    justify-content: center;
    align-items: center;
}

input,
p {
    display: inline-block;
    justify-content: center;
    align-items: center;
    margin-top: 5px;
}
.close{
    position: relative;
    right: 10%;
    top: 10%;
}
.container-formulario{
    width: 70%;
}
.input{
    display: flex;
    justify-content: center;
    align-items: center;
}
</style>


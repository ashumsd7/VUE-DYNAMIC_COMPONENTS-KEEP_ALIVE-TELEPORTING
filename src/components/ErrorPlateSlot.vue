<template>
    <div>
        <dialog open>
            <slot></slot>
        </dialog>
    </div>
</template>

<style scoped>
dialog{
    position:fixed;
    margin: 0;
    top:20vh;
    left:30%;
    width: 35%;
    background: black;
    color: white;
    padding: 1rem;
}
</style>
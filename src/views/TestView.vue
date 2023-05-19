<script setup lang="ts">
import { ref} from 'vue';

let email = ref<string>();
let pass = ref<string>();;

</script>

<template>
    
<form action="">
    <label for="email">
        Email:
        <input type="text" v-model="email" name="email" autocomplete="email">
    </label>
    <label for="current-password">
        Password:
        <input type="password" v-model="pass" name="current-password" autocomplete="current-password">
    </label>
    
</form>

<div>Your email {{ email }}</div>
<div>Your password {{ pass }}</div>
</template>

<style scoped lang="scss">
form{

    display: flex;
    
    flex-direction: column;
    width: 100%;
    label{
        width: 100%;
    }
}

</style>

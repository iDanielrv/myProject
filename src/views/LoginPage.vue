<script setup>
import router from '@/router';
import { ref } from 'vue'


let password = ref(null);
let email = ref(null);


let show1 = ref(false);

let rules = (value) => {
    if (value) return true

    return 'Este campo é obrigatorio'
}

let handleSubmit = (e) => {
    e.preventDefault();
    console.log('erro ao cadastrar');
}

</script>

<template>
    <div class="container">
        <v-form validate-on="submit">
            <v-card class="registerBox" elevation="20">
            <v-card
                class="mx-auto cardContent"
                title="User Login"
                width="444"
                height="400"
                elevation="0"
            >
            <v-container>     
                    <v-text-field
                        v-model="email"
                        label="Email"
                        :rules="[rules]"
                        color="primary"
                        variant="underlined"
                    ></v-text-field>
    
                    <v-text-field
                        v-model="password"
                        color="primary"
                        :rules="[rules]"
                        label="Password"
                        placeholder="Enter your password"
                        :append-icon="show1 ? 'mdi-eye' : 'mdi-eye-off'"
                        :type="show1 ? 'text' : 'password'"
                        @click:append="show1 = !show1"
                        variant="underlined"
                    ></v-text-field>
                </v-container>
                <v-divider></v-divider>
    
                <v-card-actions>
                <v-spacer></v-spacer>
    
                <v-btn color="success" type="submit" @click="handleSubmit">
                    Login
                    <v-icon icon="mdi-chevron-right" end></v-icon>
                </v-btn>
                </v-card-actions>
            </v-card>
        </v-card>
        </v-form>
        
    </div>
</template>

<style scoped>

.registerBox {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 37.875rem;
    width: 37.875rem;
    background-color: #33333300;
}

.cardContent {
    background-color: #33333300;
    color: white;
    border: none;
}

</style>


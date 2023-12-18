<script setup>
import router from '@/router';
import { ref } from 'vue';
import axios from 'axios';



let username = ref(null);
let email = ref(null);
let password = ref(null);
let confirmPassword = ref(null);
let terms = ref(false);


let show1 = ref(false);
let show2 = ref(false);

let rules = (value) => {
    if (value) return true   
    return 'Este campo é obrigatorio'
}


let handleSubmit = (e) => {

    if (username.value && email.value && password.value != null) {
        axios.post('http://localhost:4000/register', {
        username: username,
        email: email,
        password: password
        })
        .then(function (response) {
            console.log(response);
            console.log('passei por aq');
        })
        .then(() => {
            router.push('/');
        })
        .catch(function (error) {
            console.log(error);
        })
    }
    
    console.log('hooi');
}


</script>

<template>
    <div class="container">
        <v-form @submit.prevent="handleSubmit" validate-on="lazy submit">
            <v-card class="registerBox" elevation="20">
            <v-card
                class="mx-auto cardContent"
                title="User Registration"
                max-width="344"
                elevation="0"
            >
            <v-container> 
                    <v-text-field
                        v-model="username"
                        label="Username"
                        :rules="[rules]"
                        color="primary"
                        variant="underlined"
                    ></v-text-field>
    
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
    
                    <v-text-field
                        v-model="confirmPassword"
                        color="primary"
                        label="Confirm Password"
                        :rules="[rules]"
                        placeholder="Enter your password"
                        :append-icon="show2 ? 'mdi-eye' : 'mdi-eye-off'"
                        :type="show2 ? 'text' : 'password'"
                        @click:append="show2 = !show2"
                        variant="underlined"
                        :persistent-hint='true'
                        hint="oioi"
                    ></v-text-field>
    
                    <v-checkbox
                        :rules="[rules]"
                        v-model="terms"
                        color="secondary"
                        label="I agree to site terms and conditions"
                    ></v-checkbox>
                </v-container>
    
                <v-divider></v-divider>
    
                <v-card-actions>
                <v-spacer></v-spacer>
    
                <v-btn color="success" type="submit">
                    Register
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
    border-radius: 25px;
}

.cardContent {
    background-color: #33333300;
    color: white;
    border: none;
}

</style>


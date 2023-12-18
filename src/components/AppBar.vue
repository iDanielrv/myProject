<template>
    <v-layout>
            <v-app-bar scroll-behavior="elevate" elevation="8" color="#2B2B2B">
              <v-app-bar-title>
                <div class="appBarTitle">
                  <router-link to="/" class="linkTitle">TaskHub</router-link>
                </div>
              </v-app-bar-title>
              <div class="appBarBtns">
                <div class="loginBtn">
                  <v-btn to="/register">Register</v-btn>
                </div>
                <div class="registerBtn">
                  <v-btn to="/login">Log in</v-btn>
                </div>
              </div>
            </v-app-bar>
    </v-layout>
</template>

<style scoped>

.linkTitle {
  color: white;
  text-decoration: none; /* no underline */
}

.linkTitle:hover {
  color: #8685EF;
}

.appBarStyle {
  background-color: black;
}
.appBarTitle {
    height: 2.125rem;
    width: 5.563rem;
    margin-left: 4rem;
}

.appBarBtns {
  display: flex;
  flex-direction: row;
  margin-right: 3.5rem;
}
.loginBtn {
  height: 3.125;
  width: 10.938;
  margin-right: 1rem;
  border-radius: 10px;
}

.loginBtn:hover {
  background-color: #8685EF;
}

.registerBtn {
  background-color: #8685EF;
  border-radius: 10px;
}

.registerBtn:hover {
  background-color: #bfaff264;
}

</style>

<script>
export default {
    name: 'AppBar'
}
</script>
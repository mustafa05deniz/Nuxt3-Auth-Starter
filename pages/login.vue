<script setup lang="ts">
import { useAuth } from "~~/composable/useAuth";

definePageMeta({
  layout: "login",
});
const { login } = useAuth();

const form = ref({
  email: "",
  password: "",
});
</script>

<template>
  <div>
    <main class="form-signin w-100 h-100 m-auto container">
      <div class="row">
        <div class="col-6 offset-3">
          <form class="" @submit.prevent="login(form)">
            <div class="form-floating">
              <input
                id="floatingInput"
                v-model="form.email"
                type="email"
                class="form-control"
                placeholder="name@example.com"
              />
              <label for="floatingInput">Email</label>
            </div>
            <div class="form-floating">
              <input
                id="floatingPassword"
                v-model="form.password"
                type="password"
                class="form-control my-3"
                placeholder="Password"
              />
              <label for="floatingPassword">Password</label>
            </div>
            <button
              class="w-100 btn btn-lg btn-primary"
              :disabled="!(form.email && form.password)"
              type="submit"
            >
              Login
            </button>
          </form>
        </div>
      </div>
    </main>
  </div>
</template>

<style scoped>
.bd-placeholder-img {
  font-size: 1.125rem;
  text-anchor: middle;
  -webkit-user-select: none;
  -moz-user-select: none;
  user-select: none;
}

@media (min-width: 768px) {
  .bd-placeholder-img-lg {
    font-size: 3.5rem;
  }
}

.b-example-divider {
  height: 3rem;
  background-color: rgba(0, 0, 0, 0.1);
  border: solid rgba(0, 0, 0, 0.15);
  border-width: 1px 0;
  box-shadow: inset 0 0.5em 1.5em rgba(0, 0, 0, 0.1),
    inset 0 0.125em 0.5em rgba(0, 0, 0, 0.15);
}

.b-example-vr {
  flex-shrink: 0;
  width: 1.5rem;
  height: 100vh;
}

.bi {
  vertical-align: -0.125em;
  fill: currentColor;
}

.nav-scroller {
  position: relative;
  z-index: 2;
  height: 2.75rem;
  overflow-y: hidden;
}

.nav-scroller .nav {
  display: flex;
  flex-wrap: nowrap;
  padding-bottom: 1rem;
  margin-top: -1px;
  overflow-x: auto;
  text-align: center;
  white-space: nowrap;
  -webkit-overflow-scrolling: touch;
}
</style>

<script setup lang="ts">
import { ref } from "vue";

const props = defineProps({
  msg: String,
});

const counter = ref(0);

const handleCounterChange = (amount: number) => {
  if (counter.value + amount > 0) {
    counter.value += amount;
  } else {
    counter.value = 0;
  }
};
</script>



<template>
  <div class="vue-div">
    <div class="logo">
      <a href="http://vue.dev">
        <img src="images/vue.png" class="vue" alt="image" />
      </a>
    </div>
    <div>
      <h1>{{ props.msg }}</h1>
      <div class="ts-div">
        <p>Learn Vue with</p>
        <div className="ts">
              <img src="images/Typescript.png" alt="Typescript" />
            </div>
        at
        <pre class="apps">src/app.vue</pre>
      </div>
      <div class="buttons">
        <button @click="handleCounterChange(1)">+1</button>
        <button>
          Count :
          <span :class="{ yellow: counter > 0, red: counter < 0 }">{{
            counter
          }}</span>
        </button>
        <button @click="handleCounterChange(-1)">-1</button>
      </div>
    </div>
    <div class="logo">
      <a href="http://webpack.js.org">
        <img src="images/webpack.png" class="webpack" alt="" />
      </a>
    </div>
  </div>
  <div class="footer">
    <div class="version">version 1.0.6</div>
    <div class="github">
      <div class="gitlogo">
        <img src="images/github.png" class="git" alt="github" />
      </div>
      <p>Codespace</p>
    </div>
  </div>
</template>

<style scoped>
/* Add your scoped CSS styles here */
</style>

<style scoped>
h1 {
  font-weight: 500;
  color: white;
  font-size: 3vw;
}

.ts-div {
  display: flex;
  color: white;
  align-items: center;
  gap: 1rem;
  text-align: center;
}

.ts-div p {
  margin: 0;
}

.ts {
  width: 1.5rem;
}

img {
  max-width: 100%;
  height: auto;
  will-change: filter;
  transition: filter 300ms;
}

.vue:hover {
  filter: drop-shadow(0 0 2em #4af36faa);
}

.webpack:hover {
  filter: drop-shadow(0 0 2em #e1eef2aa);
}

.vue-div {
  display: flex;
  gap: 1rem;
  align-items: center;
  justify-content: center;
}

.vue-div .logo {
  width: 8rem;
  height: auto;
}

.apps,
button {
  padding: 5px 10px;
  background-color: #0c2519;
  border-radius: 5px;
  color: white;
}

.logo {
  width: 8rem;
}

.buttons {
  display: flex;
  align-items: center;
  margin-top: 2rem;
  gap: 0.5rem;
}

.buttons :nth-of-type(1),
.buttons :nth-of-type(3) {
  cursor: pointer;
}

.buttons :nth-of-type(1):hover,
.buttons :nth-of-type(3):hover {
  background-color: #2a914e;
}

button {
  border: none;
  box-shadow:
    rgba(0, 0, 0, 0.25) 0px 54px 55px,
    rgba(0, 0, 0, 0.12) 0px -12px 30px,
    rgba(0, 0, 0, 0.12) 0px 4px 6px,
    rgba(0, 0, 0, 0.17) 0px 12px 13px,
    rgba(0, 0, 0, 0.09) 0px -3px 5px;
}

.yellow {
  color: rgb(255, 255, 1);
}

.red {
  color: rgb(253, 53, 53);
}

.footer {
  display: flex;
  justify-content: space-between;
  align-items: center;
  position: absolute;
  bottom: 1%;
  left: 1%;
  right: 1%;
  color: white;
}

.footer .github {
  display: flex;
  align-items: center;
  gap: 0.5rem;
}

.footer .github p {
  margin: 0;
}

.footer .git {
  filter: drop-shadow(0 0 2em #fcfcfc);
}

.footer .gitlogo {
  width: 6rem;
  height: 100%;
  display: flex;
  align-items: center;
}

.footer .gitlogo img {
  width: 100%;
  height: auto;
}

.version {
  font-weight: 400;
}

@media screen and (max-width: 1084px) {
  h1 {
    font-size: 2.5rem;
  }

  .vue-div {
    text-align: center;
    justify-content: center;
    align-items: center;
  }

  .buttons {
    width: 100%;
  }
}

@media screen and (max-width: 730px) {
  .vue-div h1 {
    font-size: 2rem;
  }
}

@media screen and (max-width: 630px) {
  .vue-div {
    flex-direction: column;
    transition: all 0.5s;
    text-align: center;
  }
}

@media screen and (max-width: 498px) {
  .buttons {
    justify-content: center;
    align-items: center;
  }
}
</style>

<template>
  <div class="container">
    <div class="joke">
      <div class="joke__body">
        <img class="joke__user" v-bind:src="`/src/components/assets/users0${index}.png`" />
        <p class="joke__text">{{ vtip }}</p>
      </div>
      <div class="joke__likes">
        <button id="btn-up" class="btn-like btn-like--up" v-on:click="likeplus"></button>
        <span id="likes-up" class="likes-count likes-count--up">{{like}}</span>
        <button id="btn-down" class="btn-like btn-like--down" v-on:click="unlikeplus"></button>
        <span id="likes-down" class="likes-count likes-count--down">{{unlike}}</span>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Jokes",
  props: {
    vtip: String,
    like: Number,
    unlike: Number
  },
  data() {
    return {
      index: 1
    };
  },
  methods: {
    likeplus() {
      this.$emit("likeJedna", this.like++);
    },
    unlikeplus() {
      this.$emit("unlikeJedna", this.unlike++);
    }
  }
};
</script>
<style>
html {
  font-family: sans-serif;
}

.container {
  max-width: 30rem;
  margin: 5rem auto;
}

.joke {
  margin-bottom: 2rem;
}

.joke__body {
  display: flex;
}

.joke__user {
  flex: 0 0 auto;
  width: 5rem;
  height: 5rem;
  margin-right: 1rem;
}

.joke__text {
  background-color: cornflowerblue;
  color: white;
  border-radius: 1rem;
  padding: 1.5rem 2rem;
  margin: 0;
  line-height: 150%;
}

.joke__likes {
  display: flex;
  justify-content: flex-end;
  align-items: center;
  margin-top: 1rem;
}

.likes-count {
  font-size: 1.5rem;
  font-weight: bold;
  margin: 0 0.5rem;
}

.likes-count--up {
  color: #00e268;
}

.likes-count--down {
  color: #ff5654;
}

.btn-like {
  border: none;
  outline: none;
  width: 2rem;
  height: 2rem;
  border-radius: 1rem;
  background-size: 1.2rem;
  background-position: center;
  background-repeat: no-repeat;
}

.btn-like--up {
  background-color: #00e268;
  background-image: url("/src/components//img/like-up.png");
}

.btn-like--down {
  background-color: #ff5654;
  background-image: url("/src/components//img/like-down.png");
}
</style>
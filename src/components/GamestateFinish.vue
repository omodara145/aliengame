<template>
  <div class="modal">
    <div v-if="uiState === 'won'">
      <h1 id="header">You're an alienzombie.</h1>
      <p>
        In order to survive on Earth, you have to pretend to be a human on this
        planet. You took over the body of a nearby hooman, but the trouble is, their
        best friend showed up!
      </p>
      <p>
        They look suspicious. Answer the questions right to make sure identity is
        kept secret!
      </p>
    </div>
    <svg
      v-else
      xmlns="http://www.w3.org/2000/svg"
      viewBox="0 0 131 131"
      aria-labelledby="face"
      role="presentation"
      width="70"
      height="70"
    >
      <title id="face">Face Icon</title>
      <defs>
        <style>
          .cls-1 {
            fill: #fbb040;
            stroke: #231f20;
          }

          .cls-1,
          .cls-3 {
            stroke-miterlimit: 10;
            stroke-width: 3px;
          }

          .cls-2 {
            fill: #231f20;
          }

          .cls-3 {
            fill: none;
            stroke: #be1e2d;
          }
        </style>
      </defs>
      <circle class="cls-1" cx="65.5" cy="65.5" r="64" />
      <circle class="cls-2" cx="95" cy="65.8" r="7.5" />
      <circle class="cls-2" cx="36" cy="65.8" r="7.5" />
      <path
        :class="['cls3', uiState === 'won' ? 'frown' : '']"
        d="M51,97s6,10,23,10S95,97,95,97"
        transform="translate(-8.5 -5.5)"
      />
    </svg>
    <p>
      <button @click="restart">Let's play again!</button>
    </p>
  </div>
</template>

<script>
import { mapState } from 'vuex'

export default {
  name: 'GamestateFinish',
  computed: {
    ...mapState(['uiState'])
  },
  methods: {
    restart () {
      this.$store.commit('reset')
    }
  }
}
</script>

<style scoped>

</style>

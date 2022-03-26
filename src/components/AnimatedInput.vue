<template>
  <section>
    <div class="wrapper">
      <input
        ref="input"
        :text="input.length || isInputFucused ? 'true' : 'false'"
        @blur="onInputBlur"
        @focus="onInputFocus"
        v-model="input"
        :type="currentType"
        style=""
      />
      <label @click="this.$refs.input.focus()">{{ placeholder }}</label>
      <div
        @mouseup="eyeOpened = false"
        @mousedown="eyeOpened = true"
        class="eye show"
        v-if="type == 'password' && input"
      >
        <img
          v-if="eyeOpened"
          src="https://img.icons8.com/material-outlined/64/000000/visible--v1.png"
        />

        <img
          v-else
          src="https://img.icons8.com/small/64/000000/closed-eye.png"
        />
      </div>
    </div>
    {{ input.legnth }}
  </section>
</template>

<script>
  export default {
    props: {
      placeholder: {
        required: false,
        type: String,
        default: "",
      },

      type: {
        required: false,
        default: "text",
        type: String,
      },
    },

    data() {
      return {
        input: "",
        isInputFucused: false,
        eyeOpened: false,
      };
    },

    computed: {
      currentType() {
        return this.eyeOpened ? "text" : this.type;
      },
    },

    methods: {
      onInputFocus() {
        this.isInputFucused = true;
      },

      onInputBlur() {
        this.isInputFucused = false;
      },
    },
  };
</script>

<style scoped>
  @keyframes show {
    from {
      opacity: 0;
    }

    50% {
      opacity: 0;
    }

    to {
      opacity: 1;
    }
  }

  .show {
    animation-name: show;
    transition: 0.2;
    animation-duration: 0.2s;
  }

  label {
    position: absolute;
    align-self: center;
    padding-left: 15px;
    transform-origin: top left;
    color: grey;
    transition: 0.2s;
    cursor: pointer;
  }

  input {
    padding-bottom: 0px;
  }

  input[text="true"] + label {
    transform: translate(2px, -15px) scale(0.8);
    /* top: 2px; */
    /* left: 2px; */
    /* transform: scale(0.8); */
  }

  .wrapper {
    display: flex;
    position: relative;
  }

  .eye {
    align-self: center;
    position: absolute;
    right: 25px;
    display: block;
    height: auto;
  }

  .eye img {
    vertical-align: middle;
    opacity: 0.5;
    width: 27px;
  }
</style>

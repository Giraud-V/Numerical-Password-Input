<template>
  <div class="hello">
    <h1>Numerical password</h1>
    <div id="card">
      <PasswordViewer :currentPassword="counter" />
      <div id="numGrid">
        <RandomizedNumericInput :currentPassword="counter" @current-password-change="setValue" />
      </div>
    </div>
  </div>
</template>

<script>
import PasswordViewer from "./PasswordViewer.vue"
import RandomizedNumericInput from "./RandomizedNumericInput.vue"
export default {
  components: {PasswordViewer, RandomizedNumericInput},
  data () {
        return {
            counter: "",
        }
    },
  methods: {
    setValue(payload) {
            if (this.userPassword != payload.counter.toString()) {
              this.counter = payload.counter
                if (payload.counter.length >= 9) {
                  this.counter = ""
                  window.location.reload()
                }
            } else {
              this.counter = payload.counter
              console.log("test")
              this.$emit('password-match', "Le mot de passe est bon")
            }
        },
  },
  name: 'NumericalPasswordInput',
  props: {
    userPassword: String
  }
}
</script>

<style scoped>
#card {
  width: 700px;
  height: 700px;
  background-color: #C1C1C1;
  padding: 50px;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
}

#valueScreen {
  width: 100%;
  height: 75px;
  background-color: #ffffff;
}

#numGrid {
  margin-top: 50px;
  width: 100%;
  height: 100%;
}

.bv-example-row {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  height: 100%;
}

.gridRow {
  height: 30%;
  width: 104%;
  display: flex;
  flex-direction: row;
  justify-content: space-between;
}

.center {
  display: flex;
  flex-direction: column;
  justify-content: center;
}



.col {
  font-size: 28px;
  font-weight: bold;
  background-color: #ffffff;
  width: 100%;
  height: 100%;
}

.col:hover {
  background-color: #5EBA90;
  cursor: pointer;
}

.col:active {
  background-color: #6C6C6C;
}
</style>

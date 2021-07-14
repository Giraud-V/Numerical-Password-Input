<template>
    <div style="width: 100%; height: 100%;">
        <div class="container">
            <div class="row">
                <div class="col center" v-for="item in items" :key="item.id" @click="add( item )"><p v-if="item >= 0">{{ item }}</p></div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
  name: 'RandomizedNumericInput',
  props: {
    currentPassword: String
  },
  data() {
    return {
      items: [1, 2, 3, 4, 5, 6, 7, 8, 9, 0, -1, -1 ].sort(() => Math.random() - 0.5)
    }
  },
  methods: {
        add(value) {
            if (value >= 0)
                this.$emit('current-password-change', { counter: this.currentPassword.toString() + value.toString() })
        },
    }
}
</script>

<style scoped>
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

.container {
    width: 100%;
    height: 100%;
}

.row {
    width: 100%;
    height: 33%;
}

@media only screen and (min-width:600px) {
  .container .col {
    float: left;
    width: 50%;
  }
}

@media only screen and (min-width:768px) {
  .container .col {
    width: 33.333%;
  }
}

@media only screen and (min-width:992px) {
  .container .col {
    width: 25%;
  }
}
</style>

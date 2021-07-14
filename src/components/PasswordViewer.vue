<template>
    <div id="valueScreen">
        <p class="screenV">{{currentPassword}}</p>
    </div>
</template>

<script>
export default {
    
    name: 'PasswordViewer',
    props: {
        currentPassword: String
    },
    methods: {
    },
}
</script>

<style scoped>
.screenV {
  border: 0;
  width: 100%;
  height: 100%;
  text-align: center;
  font-size: 24px;
}
</style>
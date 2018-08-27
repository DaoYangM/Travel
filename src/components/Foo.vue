<template>
  <div class="hello">
    <h1>FOOOOOOO</h1>
    <child></child>
    <router-link to='/hello-world'>GO TO HELLO WORLD 123123123</router-link>
  </div>
</template>

<script>
let child = {
  template: '<h2>CHILD</h2>'
}
export default {
  name: 'Foo',
  components: {
    'child': child
  }
}
</script>

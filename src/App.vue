<template>
    <div>
        <Todo/>
    </div>
</template>

<script>
import ToDo from "@/components/Todo";
export default {
  name: 'App',
  components: {
      Todo:ToDo,
  }
}
</script>

<style>
#app {

}
</style>

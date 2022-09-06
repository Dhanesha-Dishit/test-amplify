<template>
  <div>
    <!-- <Tutorial /> -->
    {{ allTodos }}
  </div>
</template>

<script>
import Amplify from '@aws-amplify/core'
import { DataStore } from '@aws-amplify/datastore'
import { Todo } from './../models'
// import awsConfig from './aws-exports'
export default {
  name: 'IndexPage',
  async mounted() {
    // for (let i = 0; i <= 10; i++)
    //   DataStore.save(
    //     new Todo({
    //       description: `Test todo ${Math.random()
    //         .toString(36)
    //         .substring(2, 5)}`,
    //     })
    //   )
    this.allTodos = await DataStore.query(Todo)
    console.log(this.allTodos, 'alltodos')
  },
  data() {
    return {
      allTodos: null,
    }
  },
}
</script>

<template>
  <div class="app-container">
    <address-book-list />
  </div>
</template>

<script>
import AddressBookList from '../../components/interaction/AddressBookList'
export default {
  name: 'AddressBook',
  components: { AddressBookList },
  data() {
    return {
      studentList: [
        {
          id: '1',
          name: '小洪'
        },
        {
          id: '1',
          name: '小洪'
        },
        {
          id: '1',
          name: '小洪'
        },
        {
          id: '1',
          name: '小洪'
        },
        {
          id: '1',
          name: '小洪'
        },
        {
          id: '1',
          name: '小洪'
        },
        {
          id: '1',
          name: '小洪'
        },
        {
          id: '1',
          name: '小洪'
        },
        {
          id: '1',
          name: '小洪'
        },
        {
          id: '1',
          name: '小洪'
        },
        {
          id: '1',
          name: '小洪'
        },
        {
          id: '1',
          name: '小洪'
        },
        {
          id: '1',
          name: '小洪'
        },
        {
          id: '1',
          name: '小洪'
        },
        {
          id: '1',
          name: '小洪'
        },
        {
          id: '1',
          name: '小洪'
        },
        {
          id: '1',
          name: '小洪'
        }
      ]
    }
  }
}
</script>

<style scoped>

</style>

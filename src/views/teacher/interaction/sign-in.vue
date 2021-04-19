<template>
  <div class="app-container">
    <aside>
      <span>2021.04.16 - 下午</span>
    </aside>
    <sign-in-table-by-teacher style="margin-bottom: 5px" />
    <sign-in-table-by-home />

    <aside style="margin-top: 20px;">
      <span>2021.04.16 - 上午</span>
    </aside>
    <sign-in-table-by-teacher style="margin-bottom: 5px" />
    <sign-in-table-by-home />
  </div>
</template>

<script>
import SignInTableByTeacher from '../../components/interaction/SignInTableByTeacher'
import SignInTableByHome from '../../components/interaction/SignInTableByHome'
export default {
  name: 'SignIn',
  components: { SignInTableByHome, SignInTableByTeacher }
}
</script>

<style scoped>

</style>

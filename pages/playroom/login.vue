<template lang="pug">
  .login-page
    img.title(
      src="/vue-static/playroom/licons-9.png"
    )
    login-form
</template>

<script>
import { mapState } from 'vuex'

export default {
  name: 'LoginPage',
  computed: {
    ...mapState({
      isGuest: state => state.user.isGuest
    })
  },
  watch: {
    isGuest () {
      console.log('this.isGuest', this.isGuest)
      if (!this.isGuest) {
        this.$router.push('/playroom')
      }
    }
  }
}
</script>

<style lang="scss" scoped>
  @import '../../assets/variables';
  .login-page {
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    padding-bottom: 13rem;
    display: flex;
    flex-flow: column;
    align-items: center;
    justify-content: center;
    background: $color-main;
    //background: linear-gradient(to bottom, #fab005 0%,$color-main 42%,#ffffff 42%,#ffffff 100%);
    background: linear-gradient(to top, #48c6ef 0%, #6f86d6 100%);
  }
  .logo {
    fill: $color-main;
    height: 120px;
    padding: 1rem;
    background: white;
    border-radius: 1.5rem;
    box-shadow: 0 1px 24px -8px rgba(0,0,0,0.3);
    margin-bottom: 1rem;
  }
  .title {
    width: 240px;
    margin-bottom: 1rem;
  }
  .login-form {
    width: 320px;
  }
</style>

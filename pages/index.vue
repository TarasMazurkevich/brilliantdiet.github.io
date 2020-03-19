<template>
  <div class="container">
    <Header />
    <main class="main">
      <Clients />
      <Programs />
      <Team />
    </main>
    <Footer />
  </div>
</template>

<script>

import Header from '~/components/sections/Header'
import Programs from '~/components/sections/Programs'
import Clients from '~/components/sections/Clients'
import Team from '~/components/sections/Team'
import Footer from '~/components/sections/Footer'

export default {
  components: {
    Header,
    Programs,
    Clients,
    Team,
    Footer
  }
}
</script>

<style>

</style>

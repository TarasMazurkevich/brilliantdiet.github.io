<template>
  <footer class="footer">
    <p class="footer-copy">
      Copyright © brilliantdiet.com 2020
    </p>
    <a class="footer-social">Instagram</a>
  </footer>
</template>

<script>

</script>

<style lang="scss">
  $padding: 1em;

  .footer {
    display: flex;
    flex-direction: column-reverse;
    margin-top: 1em;
    padding: $padding;
    background-color: #0a2e24;
    font-family: 'Ubuntu', sans-serif;
    color: #fff;

    @media only screen and (min-width: 991px) {
      margin-top: 0;
    }

    &-copy {
      margin-top: .5em;
      font-size: 14px;
    }

    &-social {
      color: #f1bd7d;
    }
  }
</style>

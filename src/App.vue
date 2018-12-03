<template>
  <div class="domain__choice">
      <div class="brand">
          <div class="section__img"></div>
          <h1>Dynki</h1>
      </div>

      <section class="section">
          <div class="main__form">
                <router-view/>
          </div>
          <div class="main__pic"></div>
      </section>
  </div>
</template>

<style lang="scss">
  @import "styles";
</style>

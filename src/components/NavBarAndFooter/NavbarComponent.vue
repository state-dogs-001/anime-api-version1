<template>
  <div>
    <b-navbar toggleable="lg" type="dark" variant="warning" fixed="top">
      <b-navbar-brand style="text-transform: uppercase" href="/">
        Anime API Test
      </b-navbar-brand>

      <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>

      <b-collapse id="nav-collapse" is-nav>
        <!-- Right aligned nav items -->
        <b-navbar-nav class="ml-auto">
          <b-nav-form @submit.stop.prevent="searchHandle">
            <div class="input-group">
              <b-form-input
                size="sm"
                class="my-2 my-sm-0"
                v-model="value"
                placeholder="Search Anything?"
              ></b-form-input>
              <div class="input-group-append">
                <b-button
                  size="sm"
                  class="my-2 my-sm-0"
                  type="submit"
                  variant="success"
                  >Search</b-button
                >
              </div>
            </div>
          </b-nav-form>
        </b-navbar-nav>
      </b-collapse>
    </b-navbar>
  </div>
</template>

<script>
export default {
  data: () => ({
    value: null,
  }),
  methods: {
    searchHandle() {
      this.$emit("searchHandle", {
        textSearch: this.value,
      });
    },
  },
};
</script>

<style>
</style>
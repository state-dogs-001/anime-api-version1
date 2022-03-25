<template>
  <div id="app">
    <div class="app-top">
      <NavBarComponent @searchHandle="searchHandle" />
    </div>
    <div class="app-main mt-5">
      <HomeComponent :data="dataSlice" />
      <!-- Paginates -->
      <div class="d-flex justify-content-center mt-5">
        <nav aria-label="Page navigation example">
          <ul class="pagination">
            <li class="page-item">
              <button class="page-link" aria-label="Previous" @click="prePage">
                <span aria-hidden="true">&laquo;</span>
              </button>
            </li>
            <li
              class="page-item"
              v-for="page in Math.ceil(data.length / perPage)"
              :key="page"
            >
              <button class="page-link" @click="pageNumber(page)">{{ page }}</button>
            </li>
            <li class="page-item">
              <button class="page-link" aria-label="Next" @click="nextPage">
                <span aria-hidden="true">&raquo;</span>
              </button>
            </li>
          </ul>
        </nav>
      </div>
    </div>
    <div class="app-bottom">
      <FooterComponent />
    </div>
  </div>
</template>

<script>
import NavBarComponent from "./components/NavBarAndFooter/NavbarComponent.vue";
import HomeComponent from "./components/HomeComponent.vue";
import FooterComponent from "./components/NavBarAndFooter/FooterComponent.vue";

export default {
  name: "App",
  components: {
    NavBarComponent,
    HomeComponent,
    FooterComponent,
  },
  data: () => ({
    data: [],

    page: 1,
    perPage: 6,
  }),
  mounted() {
    fetch("https://jikan1.p.rapidapi.com/top/anime/1/upcoming", {
      method: "GET",
      headers: {
        "Content-Type": "application/json",
        "X-RapidAPI-Host": "jikan1.p.rapidapi.com",
        "X-RapidAPI-Key": "e2245fb5f0msh2c226b5b48da0e1p1c1f26jsne0a310747a03",
      },
    })
      .then((response) => response.json())
      .then((data) => {
        this.data = data.top;
      });
  },
  computed: {
    dataSlice: function () {
      let start = (this.page - 1) * this.perPage,
        end = start + this.perPage;
      return this.data.slice(start, end);
    },
  },
  methods: {
    searchHandle(value) {
      this.data = this.data.filter(function (animes) {
        return animes.title.toLowerCase().match(value.textSearch.toLowerCase());
      });
    },

    prePage() {
      if (this.page > 1) {
        this.page -= 1;
      }
    },
    nextPage() {
      if (this.page < Math.ceil(this.data.length / this.perPage)) {
        this.page += 1;
      }
    },
    pageNumber(page) {
      this.page = page
    },
  },
};
</script>

<style>
@import url("https://fonts.googleapis.com/css2?family=Josefin+Sans&display=swap");
#app {
  font-family: "Josefin Sans", sans-serif;
  background: url("https://wallpaperaccess.com/full/1971385.jpg") no-repeat
    center center fixed;
  -webkit-background-size: cover;
  -moz-background-size: cover;
  -o-background-size: cover;
  background-size: cover;
}
</style>

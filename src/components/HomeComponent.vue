<template>
  <div>
    <b-container>
      <b-row>
        <b-col
          lg="4"
          md="6"
          sm="12"
          v-for="anime in data"
          :key="anime.mal_id"
          class="my-3 d-flex justify-content-center"
        >
          <b-card
            :title="anime.title"
            :img-src="anime.image_url"
            :img-alt="anime.title"
            img-top
            tag="article"
            style="max-width: 20rem"
            class="mb-2 mt-5"
          >
            <b-card-text> Type: {{ anime.type }} </b-card-text>

            <a
              :href="anime.url"
              target="_blank"
              variant="primary"
              class="btn btn-primary"
              >Read More</a
            >
          </b-card>
        </b-col>
      </b-row>
    </b-container>
  </div>
</template>

<script>
export default {
  props: {
    data: Array,
  },
};
</script>

<style>
.card {
  border: none;
  overflow: hidden;
}
.card img {
  height: 20rem;
  -webkit-transform: scale(1);
  transform: scale(1);
  -webkit-transition: 0.3s ease-in-out;
  transition: 0.3s ease-in-out;
}
.card img:hover {
  -webkit-transform: scale(1.1);
  transform: scale(1.1);
}
.card .card-title {
  width: 250px;
  white-space: nowrap;
  overflow: hidden;
  text-overflow: ellipsis;
}
</style>
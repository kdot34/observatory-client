
<template>
  <div class="container">
    <PageHeader title="Blog" />

    <div class="row">
      <div class="col-lg-12">

        <!-- Fetching -->
        <!-- TODO - phase this out in favor of Loading -->
        <p class='lead' v-if="fetching">
          <i class="fa fa-2x fa-spin fa-spinner"></i>
        </p>

        <!-- EmptyView -->
        <!-- TODO - abstract into ListView -->
        <p class='lead' v-if="!collection[0]">
          EMPTY
        </p>

        <a class="btn btn-primary" href='#/blogs/new'>
          New Blog
        </a>

        <!-- ListView -->
        <ListView :collection="collection"/>

      </div>
    </div>
  </div>
</template>

<!-- // // // //  -->

<script>
import ListView from './list.vue'
import { mapGetters } from 'vuex'

export default {
  props: ['collection'],
  computed: mapGetters({
    fetching: 'blog/fetching'
  }),
  components: {
    ListView
  }
}
</script>



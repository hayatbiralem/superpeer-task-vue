<template>
  <div class="c-call-details u-text-align-center">

    <!-- .c-call-details__heading -->
    <div class="c-call-details__heading" v-if="heading">
      <Heading
        class="u-margin-bottom-none"
        :prefix="heading.prefix"
        :text="heading.text"></Heading>
    </div>
    <!-- /.c-call-details__heading -->

    <!-- .c-call-details__time -->
    <div class="c-call-details__time" v-if="meta || timezone">

      <!-- .c-call-details__meta -->
      <div class="c-call-details__meta" v-if="meta">
        <MetaBox :data="meta" :is-inline="1"></MetaBox>
      </div>
      <!-- /.c-call-details__meta -->

      <!-- .c-call-details__timezone -->
      <div class="c-call-details__timezone" v-if="timezone">

        <!-- .c-tip -->
        <div class="c-tip">{{ timezone }}</div>
        <!-- /.c-tip -->

      </div>
      <!-- /.c-call-details__timezone -->

    </div>
    <!-- /.c-call-details__time -->
  </div>
</template>

<script>
import MetaBox from "./MetaBox";
import Heading from "./Heading";

export default {
  name: "CallDetails",
  props: ["data"],
  components: {
    MetaBox,
    Heading,
  },
  data() {
    return {
      heading: this.data.heading || null,
      meta: this.data.meta || null,
      timezone: this.data.timezone || null,
    };
  }
};
</script>

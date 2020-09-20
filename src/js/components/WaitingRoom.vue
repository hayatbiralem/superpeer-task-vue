<template>
  <div class="c-waiting-room">
    <Card submit-text="Join Call" @submit.native.prevent="form.submit">
      <template v-slot:header>
        <CallDetails :data="callDetails"></CallDetails>
      </template>

      <template v-slot:default>
        <VideoPreview :data="videoPreview"></VideoPreview>
        <UIForm :data="form.items"></UIForm>
      </template>

      <template v-slot:foot>
        <UIButton :is-primary="1" :is-block="1" type="submit">
          {{ submitText }}
        </UIButton>
      </template>
    </Card>
  </div>
</template>

<script>
import Card from "./Card";
import CallDetails from "./CallDetails";
import VideoPreview from "./VideoPreview";
import UIButton from "./UIButton";
import UIForm from "./UIForm";

export default {
  name: "WaitingRoom",
  props: ["data"],
  components: {
    Card,
    CallDetails,
    VideoPreview,
    UIButton,
    UIForm,
  },
  data() {
    return {
      callDetails: this.data.callDetails || null,
      videoPreview: this.data.videoPreview || null,
      form: this.data.form || null,
      submitText: this.data.submitText
    };
  }
};
</script>

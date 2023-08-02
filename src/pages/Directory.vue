<template>
  <q-page class="q-pa-sm">
    <div class="row q-col-gutter-sm">
      <div
        class="col-lg-4 col-md-4 col-xs-12 col-sm-12"
        v-for="data in card_data"
        v-bind:key="data"
      >
        <directory-card
          class="col-lg-4 fit col-md-4 col-sm-12 col-xs-12"
          :avatar="data.avatar"
          :name="data.name"
          :des="data.des"
          :email="data.email"
        ></directory-card>
      </div>
    </div>
  </q-page>
</template>

<script>
import { defineComponent, defineAsyncComponent } from "vue";

const card_data = [
  {
    name: "Prathamesh Devhare",
    Crated_Date: "2/8/2023",
    Project: "Quasar Admin",
    avatar: "src/assets/avtar.png",
    progress: 80,
    des: "Solutions Developer",
    email: "test@gmail.com",
  },
  {
    name: "Prathamesh Devhare",
    Crated_Date: "2/8/2023",
    Project: "Quasar QDraggableTree",
    avatar: "src/assets/avtar.png",
    progress: 50,
    des: "Solutions Developer",
    email: "test@gmail.com",
  },
  {
    name: "Prathamesh Devhare",
    Crated_Date: "2/8/2023",
    Project: "Quasar Shopping",
    avatar: "src/assets/avtar.png",
    progress: 100,
    des: "Solutions Developer",
    email: "test@gmail.com",
  },
  {
    name: "Jeff Galbraith",
    Crated_Date: "10/2/2019",
    Project: "Quasar QMarkdown",
    avatar:
      "https://avatars1.githubusercontent.com/u/10262924?s=400&u=9f601b344d597ed76581e3a6a10f3c149cb5f6dc&v=4",
    progress: 60,
    des: "Solutions Developer",
    email: "test@gmail.com",
  },
  {
    name: "Prathamesh Devhare",
    Crated_Date: "2/8/2023",
    Project: "Quasar QGrid",
    avatar: "src/assets/avtar.png",
    progress: 30,
    des: "Solutions Developer",
    email: "test@gmail.com",
  },
  {
    name: "Prathamesh Devhare",
    Crated_Date: "2/8/2023",
    Project: "Quasar QDraggableTree",
    avatar: "src/assets/avtar.png",
    progress: 50,
    des: "Solutions Developer",
    email: "test@gmail.com",
  },
  {
    name: "Prathamesh Devhare",
    Crated_Date: "2/8/2023",
    Project: "Quasar Shopping",
    avatar: "src/assets/avtar.png",
    progress: 100,
    des: "Solutions Developer",
    email: "test@gmail.com",
  },
  {
    name: "Jeff Galbraith",
    Crated_Date: "10/2/2019",
    Project: "Quasar QMarkdown",
    avatar:
      "https://avatars1.githubusercontent.com/u/10262924?s=400&u=9f601b344d597ed76581e3a6a10f3c149cb5f6dc&v=4",
    progress: 60,
    des: "Solutions Developer",
    email: "test@gmail.com",
  },
];

export default defineComponent({
  name: "Directory",
  components: {
    DirectoryCard: defineAsyncComponent(() =>
      import("components/cards/DirectoryCard.vue")
    ),
  },
  setup() {
    return {
      card_data,
    };
  },
});
</script>

<style scoped></style>

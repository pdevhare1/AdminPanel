<template>
  <q-card class="no-shadow" bordered>
    <q-card-section>
      <div class="text-h6 text-grey-8">Custom Grid View</div>
    </q-card-section>
    <q-separator />
    <q-card-section class="q-pa-none">
      <q-table grid :rows="data" :columns="columns" hide-bottom>
        <template v-slot:item="props">
          <div class="q-pa-xs col-xs-12 col-sm-6 col-md-4 col-lg-3">
            <card-profile
              :avatar="props.row.avatar"
              :name="props.row.name"
              :des="props.row.des"
            ></card-profile>
          </div>
        </template>
      </q-table>
    </q-card-section>
  </q-card>
</template>

<script>
import { defineComponent } from "vue";

import CardProfile from "components/cards/CardProfile.vue";

const columns = [
  { name: "Name", label: "Name", field: "name", sortable: true, align: "left" },
  {
    name: "Crated Date",
    label: "Crated Date",
    field: "Crated_Date",
    sortable: true,
    align: "left",
  },
  {
    name: "Project",
    label: "Project",
    field: "Project",
    sortable: true,
    align: "left",
  },
  {
    name: "Action",
    label: "",
    field: "Action",
    sortable: false,
    align: "center",
  },
];

const data = [
  {
    name: "Prathamesh Devhare",
    Crated_Date: "1/08/2023",
    Project: "Quasar Admin",
    avatar: "src/assets/avtar.png",
    progress: 80,
    des: "Solutions Developer",
  },
  {
    name: "Prathamesh Devhare",
    Crated_Date: "1/08/2023",
    Project: "Quasar QDraggableTree",
    avatar: "src/assets/avtar.png",
    progress: 50,
    des: "Solutions Developer",
  },
  {
    name: "Prathamesh Devhare",
    Crated_Date: "1/08/2023",
    Project: "Quasar Shopping",
    avatar: "src/assets/avtar.png",
    progress: 100,
    des: "Solutions Developer",
  },
  {
    name: "Jeff Galbraith",
    Crated_Date: "10/2/2019",
    Project: "Quasar QMarkdown",
    avatar:
      "https://avatars1.githubusercontent.com/u/10262924?s=400&u=9f601b344d597ed76581e3a6a10f3c149cb5f6dc&v=4",
    progress: 60,
    des: "Solutions Developer",
  },
  {
    name: "Prathamesh Devhare",
    Crated_Date: "1/08/2023",
    Project: "Quasar QGrid",
    avatar: "src/assets/avtar.png",
    progress: 30,
    des: "Solutions Developer",
  },
];

export default defineComponent({
  name: "TableCustomGrid",
  components: { CardProfile },
  setup() {
    return {
      columns,
      data,
    };
  },
});
</script>

<style scoped></style>

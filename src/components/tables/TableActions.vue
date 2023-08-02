<template>
  <q-card class="no-shadow" bordered>
    <q-card-section>
      <div class="text-h6 text-grey-8">
        Inline Actions
        <q-btn
          label="Export"
          class="float-right text-capitalize text-indigo-8 shadow-3"
          icon="person"
        />
      </div>
    </q-card-section>
    <q-separator></q-separator>
    <q-card-section class="q-pa-none">
      <q-table :rows="data" :columns="columns" hide-bottom class="no-shadow">
        <template v-slot:body-cell-Name="props">
          <q-td :props="props">
            <q-item style="max-width: 420px">
              <q-item-section avatar>
                <q-avatar>
                  <img :src="props.row.avatar" />
                </q-avatar>
              </q-item-section>

              <q-item-section>
                <q-item-label>{{ props.row.name }}</q-item-label>
              </q-item-section>
            </q-item>
          </q-td>
        </template>
        <template v-slot:body-cell-Action="props">
          <q-td :props="props">
            <q-btn icon="edit" size="sm" flat dense />
            <q-btn icon="delete" size="sm" class="q-ml-sm" flat dense />
          </q-td>
        </template>
      </q-table>
    </q-card-section>
  </q-card>
</template>

<script>
import { defineComponent } from "vue";

const data = [
  {
    name: "Prathamesh Devhar",
    Crated_Date: "1/08/2023",
    Project: "Quasar Admin",
    avatar: "src/assets/avtar.png",
    progress: 80,
    des: "Solutions Developer",
  },
  {
    name: "Prathamesh Devhar",
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
    Crated_Date: "1/8/2023",
    Project: "Quasar QMarkdown",
    avatar:
      "https://avatars1.githubusercontent.com/u/10262924?s=400&u=9f601b344d597ed76581e3a6a10f3c149cb5f6dc&v=4",
    progress: 60,
    des: "Solutions Developer",
  },
  {
    name: "Prathamesh Devhar",
    Crated_Date: "1/08/2023",
    Project: "Quasar QGrid",
    avatar: "src/assets/avtar.png",
    progress: 30,
    des: "Solutions Developer",
  },
];

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

export default defineComponent({
  name: "TableActions",
  setup() {
    return {
      data,
      columns,
    };
  },
});
</script>

<style scoped></style>

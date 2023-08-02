<template>
  <q-card class="table-bg no-shadow" bordered>
    <q-card-section>
      <div class="text-h6 text-white">
        Dark Mode
        <q-btn
          label="Export"
          color="blue"
          class="float-right text-capitalize shadow-3"
          icon="person"
        />
      </div>
    </q-card-section>
    <q-separator color="white" />
    <q-card-section class="q-pa-none">
      <q-table
        dark
        class="table-bg"
        :rows="data"
        :columns="columns"
        hide-bottom
      >
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
        <template v-slot:body-cell-Progress="props">
          <q-td :props="props">
            <q-linear-progress
              dark
              :color="getColor(props.row.progress)"
              :value="props.row.progress / 100"
              class="q-mt-md"
            />
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
    name: "Prathamesh Devhare",
    Crated_Date: "15/3/2020",
    Project: "Quasar Admin",
    avatar: "src/assets/avtar.png",
    progress: 80,
    des: "Solutions Developer",
  },
  {
    name: "Prathamesh Devhare",
    Crated_Date: "10/2/2018",
    Project: "Quasar QDraggableTree",
    avatar: "src/assets/avtar.png",
    progress: 50,
    des: "Solutions Developer",
  },
  {
    name: "Prathamesh Devhare",
    Crated_Date: "10/2/2018",
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
    Crated_Date: "2/08/2023",
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
    name: "Progress",
    label: "Progress",
    field: "Progress",
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
  name: "TableDarkMode",
  setup() {
    return {
      data,
      columns,

      getColor(val) {
        if (val > 70 && val <= 100) {
          return "green";
        } else if (val > 50 && val <= 70) {
          return "blue";
        }
        return "red";
      },
    };
  },
});
</script>

<style>
.table-bg {
  background-color: #162b4d;
}
</style>

<template>
  <q-card class="no-shadow" bordered>
    <q-card-section>
      <div class="text-h6 text-grey-8">Team Progress</div>
    </q-card-section>
    <q-separator />
    <q-card-section class="q-pa-none">
      <q-table class="no-shadow" :rows="data3" :columns="column" hide-bottom>
        <template v-slot:body-cell-Name="props">
          <q-td :props="props" style="max-width: 100px">
            <q-item>
              <q-item-section avatar>
                <q-avatar>
                  <img :src="props.row.avatar" />
                </q-avatar>
              </q-item-section>

              <q-item-section>
                <q-item-label>{{ props.row.name }}</q-item-label>
                <q-item-label caption class="">{{
                  props.row.des
                }}</q-item-label>
              </q-item-section>
            </q-item>
          </q-td>
        </template>
        <template v-slot:body-cell-Task="props">
          <q-td :props="props">
            <q-item>
              <q-item-section>
                <q-item-label>
                  <span class="text-blue">
                    <q-icon
                      name="bug_report"
                      color="blue"
                      size="20px"
                      v-if="props.row.type == 'error'"
                    ></q-icon>
                    <q-icon
                      name="settings"
                      color="blue"
                      size="20px"
                      v-if="props.row.type == 'info'"
                    ></q-icon>
                    <q-icon
                      name="flag"
                      color="blue"
                      size="20px"
                      v-if="props.row.type == 'success'"
                    ></q-icon>
                    <q-icon
                      name="fireplace"
                      color="blue"
                      size="20px"
                      v-if="props.row.type == 'warning'"
                    ></q-icon>
                    {{ props.row.issue }}
                  </span>
                  <q-chip
                    class="float-right text-white text-capitalize"
                    :label="props.row.type"
                    color="positive"
                    v-if="props.row.type == 'success'"
                  ></q-chip>
                  <q-chip
                    class="float-right text-white text-capitalize"
                    :label="props.row.type"
                    color="info"
                    v-if="props.row.type == 'info'"
                  ></q-chip>
                  <q-chip
                    class="float-right text-white text-capitalize"
                    :label="props.row.type"
                    color="warning"
                    v-if="props.row.type == 'warning'"
                  ></q-chip>
                  <q-chip
                    class="float-right text-white text-capitalize"
                    :label="props.row.type"
                    color="negative"
                    v-if="props.row.type == 'error'"
                  ></q-chip>
                </q-item-label>
                <q-item-label caption class="">
                  <q-linear-progress
                    dark
                    :color="getColor(props.row.Progress)"
                    :value="props.row.Progress / 100"
                  />
                </q-item-label>
              </q-item-section>
            </q-item>
          </q-td>
        </template>
      </q-table>
    </q-card-section>
  </q-card>
</template>

<script>
import { defineComponent } from "vue";

const column = [
  { name: "Name", label: "Name", field: "name", sortable: true, align: "left" },
  { name: "Task", label: "Task", field: "task", sortable: true, align: "left" },
];

const data3 = [
  {
    name: "Prathamesh Devhare",
    des: "Developer",
    Progress: 70,
    type: "info",
    issue: "#125",
    avatar: "src/assets/avtar.png",
  },
  {
    name: "Prathamesh Devhare",
    des: "Developer",
    Progress: 60,
    type: "success",
    issue: "#1425",
    avatar: "src/assets/avtar.png",
  },
  {
    name: "Prathamesh Devhare",
    des: "Developer",
    Progress: 30,
    type: "warning",
    issue: "#1475",
    avatar: "src/assets/avtar.png",
  },
  {
    name: "Jeff Galbraith",
    des: "Developer",
    Progress: 100,
    type: "success",
    issue: "#134",
    avatar:
      "https://avatars1.githubusercontent.com/u/10262924?s=400&u=9f601b344d597ed76581e3a6a10f3c149cb5f6dc&v=4",
  },
];

export default defineComponent({
  name: "TableProgress",
  setup() {
    return {
      column,
      data3,
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

<style scoped></style>

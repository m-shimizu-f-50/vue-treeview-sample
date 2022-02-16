<template>
  <v-row class="px-5">
    <v-col cols="4">
      <div class="mb-2">
        <h3>サイドメニュー</h3>
      </div>
      <v-card>
        <v-treeview selectable :items="items"> </v-treeview>
      </v-card>
    </v-col>
    <v-col cols="8">
      <div class="mb-2">
        <h3>メインメニュー</h3>
      </div>
      <v-card>
        <v-data-table
          :headers="headers"
          :items="displayItems"
          hide-default-footer
          disable-sort
          disable-pagination
        >
          <template v-slot:[`item.delete`]="{ item }">
            <v-btn small color="error" @click="deleteItem(item)"> 削除 </v-btn>
          </template>
        </v-data-table>
      </v-card>
    </v-col>
  </v-row>
</template>

<script>
export default {
  data: () => ({
    headers: [
      {
        text: "ID",
        value: "id",
      },
      {
        text: "名前",
        value: "name",
      },
      {
        text: "削除",
        value: "delete",
        sortable: false,
      },
    ],

    items: [
      {
        id: 1,
        name: "Applications :",
        children: [
          { id: 2, name: "Calendar : app" },
          { id: 3, name: "Chrome : app" },
          { id: 4, name: "Webstorm : app" },
        ],
      },
      {
        id: 5,
        name: "Documents :",
        children: [
          {
            id: 6,
            name: "vuetify :",
            children: [
              {
                id: 7,
                name: "src :",
                children: [
                  { id: 8, name: "index : ts" },
                  { id: 9, name: "bootstrap : ts" },
                ],
              },
            ],
          },
          {
            id: 10,
            name: "material2 :",
            children: [
              {
                id: 11,
                name: "src :",
                children: [
                  { id: 12, name: "v-btn : ts" },
                  { id: 13, name: "v-card : ts" },
                  { id: 14, name: "v-window : ts" },
                ],
              },
            ],
          },
        ],
      },
      {
        id: 15,
        name: "Downloads :",
        children: [
          { id: 16, name: "October : pdf" },
          { id: 17, name: "November : pdf" },
          { id: 18, name: "Tutorial : html" },
        ],
      },
      {
        id: 19,
        name: "Videos :",
        children: [
          {
            id: 20,
            name: "Tutorials :",
            children: [
              { id: 21, name: "Basic layouts : mp4" },
              { id: 22, name: "Advanced techniques : mp4" },
              { id: 23, name: "All about app : dir" },
            ],
          },
          { id: 24, name: "Intro : mov" },
          { id: 25, name: "Conference introduction : avi" },
        ],
      },
    ],
    displayItems: [
      {
        id: 1,
        name: "Applications :",
        children: [
          { id: 2, name: "Calendar : app" },
          { id: 3, name: "Chrome : app" },
          { id: 4, name: "Webstorm : app" },
        ],
      },
    ],
  }),
  methods: {
    deleteItem(item) {
      const index = this.displayItems.indexOf(item);
      window.confirm("本当に削除しますか？") &&
        this.displayItems.splice(index, 1);
    },
  },
};
</script>

<style>
</style>
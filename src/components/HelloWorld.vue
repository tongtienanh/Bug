<template>
  <v-card>
    <v-tabs
      v-model="tab"
      background-color="primary"
      dark
    >
      <v-tab
        v-for="item in items"
        :key="item.tab"
      >
        {{ item.tab }}
      </v-tab>
    </v-tabs>

    <v-tabs-items v-model="tab">
      <v-tab-item
        v-for="(item, index) in items"
        :key="item.tab"
      >
        <Item :key="item.tab" :current="tab" :tab="index" />
      </v-tab-item>
    </v-tabs-items>
  </v-card>
</template>

<script>
  import Vue from 'vue'
  import DatetimePicker from 'vuetify-datetime-picker';
  Vue.use(DatetimePicker)
  import Item from "./Item";
  export default {
    name: 'HelloWorld',
    components: {Item},
    data: () => ({
      tab: 0,
      items: [
        { tab: 'One', content: 'Tab 1 Content' },
        { tab: 'Two', content: 'Tab 2 Content' },
        { tab: 'Three', content: 'Tab 3 Content' },
        { tab: 'Four', content: 'Tab 4 Content' },
        { tab: 'Five', content: 'Tab 5 Content' },
        { tab: 'Six', content: 'Tab 6 Content' },
        { tab: 'Seven', content: 'Tab 7 Content' },
        { tab: 'Eight', content: 'Tab 8 Content' },
        { tab: 'Nine', content: 'Tab 9 Content' },
        { tab: 'Ten', content: 'Tab 10 Content' },
      ],
    }),
  }
</script>

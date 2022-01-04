<template>
  <v-card contextmenu="center">
    <DatePicker :value="null" color="red" is-range mode="dateTime" columns="2" />
  </v-card>
</template>

<script>
import Vue from "vue";
import DatetimePicker from "vuetify-datetime-picker";
Vue.use(DatetimePicker);
import DatePicker from "v-calendar/lib/components/date-picker.umd";
export default {
  name: "HelloWorld",
  components: { DatePicker },
  data: () => ({
    tab: 0,
    items: [
      { tab: "One", content: "Tab 1 Content" },
      { tab: "Two", content: "Tab 2 Content" },
      { tab: "Three", content: "Tab 3 Content" },
      { tab: "Four", content: "Tab 4 Content" },
      { tab: "Five", content: "Tab 5 Content" },
      { tab: "Six", content: "Tab 6 Content" },
      { tab: "Seven", content: "Tab 7 Content" },
      { tab: "Eight", content: "Tab 8 Content" },
      { tab: "Nine", content: "Tab 9 Content" },
      { tab: "Ten", content: "Tab 10 Content" },
    ],
  }),
};
</script>

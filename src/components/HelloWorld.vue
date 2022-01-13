<template>
  <div>
     <table>
        <thead class="ant-table-thead">
         <tr class="table-header">
          <th class="ant-table-cell-fix-left" style="background: #F2F2F2">
            <v-btn class="" width="24" height="24" icon @click="onChangeCheckboxAll">
              <v-icon
                  :class="{ 'color-checkbox': changeIcon}"
                  class="">{{ changeIcon ? 'mdi-checkbox-marked' : 'mdi-checkbox-blank-outline' }}
              </v-icon>
            </v-btn>
          </th>
        </tr>
        </thead>
      <template v-for="contact in tableComfirm">
        <tr class="table-content" :key="contact">
          <td
            class="ant-table-cell-fix-left"
            style="left: 0"
          >
            <v-btn width="24" height="24" class="mr-0" icon @click="contact.isCheck = !contact.isCheck">
              <v-icon
                :color="contact.isCheck ? '#e91e63' : ''"
                :class="{ '': changeIcon }"
                style="font-size:20px"
              >
                {{
                  contact.isCheck
                    ? "mdi-checkbox-marked"
                    : "mdi-checkbox-blank-outline"
                }}
              </v-icon>
            </v-btn>
          </td>
        </tr>
      </template>
    </table>
  </div>
</template>
<script>
export default {
  components: {
  },
  data() {
    return {
      tableComfirm:[
        {"isCheck":false},
        {"isCheck":false},
        {"isCheck":false},

      ]
    };
  },
   created() {
   
  },
  methods: {
    onChangeCheckboxAll() {
      this.changeIcon = !this.changeIcon
      this.tableComfirm.forEach(contact => contact.isCheck = !contact.isCheck)
    },
  },

};
</script>
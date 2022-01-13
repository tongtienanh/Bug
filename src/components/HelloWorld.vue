<template>
  <v-card class="schedule-filter" style="padding: 38px 60px">
    <h2>Chọn lịch làm việc</h2>
      <form class="info-class">
        <div class="info-class-item">
          <div class="info-class-item-label">
            <label for="nameHomework"
              >Thời gian áp dụng
              <v-icon>mdi-asterisk</v-icon>
            </label>
          </div>
          <v-menu
            ref="menu"
            v-model="pickDate"
            :close-on-content-click="false"
            transition="scale-transition"
            offset-y
            min-width="auto"
          >
            <template v-slot:activator="{ on, attrs }">
              <v-text-field
                type="text"
                id="nameHomework"
                clearable
                @click:clear="onClearClicked"
                v-model="dateRangeText"
                readonly
                v-bind="attrs"
                v-on="on"
                outlined
                flat
                dense
              />
            </template>
            <v-card style="z-index: 10; margin: 0">
              <v-tabs v-model="tab" class="tab-item">
                <v-tabs-slider color="yellow"></v-tabs-slider>
                <v-tab> Chọn lịch lẻ </v-tab>
                <v-tab> Chọn khoảng thời gian </v-tab>
              </v-tabs>
              <v-tabs-items v-model="tab">
                <v-tab-item>
                  <v-date-picker
                    v-model="date"
                    no-title
                    multiple
                    event-color="blue lighten-1"
                    class="pick-odd"
                  >
                  </v-date-picker>
                </v-tab-item>
                <v-tab-item>
                  <v-date-picker  
                  no-title 
                  v-model="dates" 
                  event-color="blue lighten-1"
                  range
                  class="pick-odd"
                  >
                  </v-date-picker>
                </v-tab-item>
              </v-tabs-items>
            </v-card>
          </v-menu>
        </div>
        <div class="info-class-item">
          <div class="info-class-item-label">
            <label for="request">Ca áp dụng</label>
          </div>
          <v-select
            clearable
            item-text="name"
            item-value="id"
            dense
            outlined
            id="request"
            :menu-props="{ bottom: true, offsetY: true }"
          ></v-select>
        </div>
        <div class="button">
          <v-btn
            class="button-next black--text"
            color="#E0E0E0"
            @click="closePopup"
          >
            Bỏ qua
          </v-btn>
          <v-btn
            class="button-save save"
            color="#FF6609"
            @click.prevent="handleSubmit(createHomework)"
            >Lưu lại
          </v-btn>
        </div>
      </form>
  </v-card>
</template>
<script>
export default {
  data() {
    return {
      tab: null,
      date: [],
      datesAll: [],
      pickDate: false,
      dates: [],
    };
  },
  created() {},
  computed: {
    dateRangeText: {
      get: function () {
        if (this.tab == 1) {
          return this.dates.join(' ~ ');
        }

        return this.date;
      },
      set: function () {
        
      }
    }
  },
  methods: {
    doubleClick() {},
    closePopup() {},
    onClearClicked() {
      this.date = [];
      this.dates = [];
    }
  },
  watch:{
    dates:{
      handler:function(newVal){
        if(newVal){
          this.datesAll = this.dates.join(' ~ ')
        }
      }
    }
  }
};
</script>
<style lang="scss" scoped>
.v-card {
  color: #343a40;
  font-family: Roboto;
  letter-spacing: 0em;
  font-style: normal;
  border-radius: 8px;

  h2 {
    font-size: 32px;
    font-weight: 400;
    line-height: 38px;
    text-align: center;
    margin-bottom: 28px;
  }

  .info-class-item {
    display: flex;

    i.v-icon.notranslate.mdi.mdi-asterisk.theme--light {
      position: absolute;
      font-size: 9px;
      color: #343a40;
    }

    .info-class-item-label {
      width: 211px;
    }

    input {
      height: 36px;
      border: 1px solid #b4b4b4;
      border-radius: 4px;
      padding-left: 12px;
      width: 519px;
      margin-bottom: 24px;
      outline: none;
    }

    .v-input {
      -webkit-box-align: start;
      -ms-flex-align: start;
      align-items: flex-start;
      display: -webkit-box;
      display: -ms-flexbox;
      display: block;
      -webkit-box-flex: 1;
      -ms-flex: 1 1 auto;
      flex: none;
    }

    .IDHomework {
      display: inline-grid;
      width: 519px;
      margin-bottom: 6px;

      input {
        width: 100%;
        margin-bottom: 0px;

        &::placeholder {
          font-family: Roboto;
          font-size: 15px;
          font-style: italic;
          font-weight: 400;
          line-height: 18px;
          letter-spacing: 0em;
          text-align: left;
          color: #a0a3bd;
        }
      }

      span {
        font-family: Roboto;
        font-size: 12px;
        font-style: normal;
        font-weight: 400;
        line-height: 20px;
        letter-spacing: 0em;
        text-align: left;
        width: 500px;

        a {
          font-weight: 700;
        }
      }
    }
  }
}

.button {
  font-size: 14px;
  font-style: normal;
  font-weight: 700;
  line-height: 20px;
  letter-spacing: 0em;
  text-align: center;
  margin: auto;
  left: 0;
  right: 0;
  bottom: 47px;

  .button-next {
    width: 130px;
    background: #e0e0e0;
    height: 32px;
    color: #333333;
    border-radius: 24px;
    margin-right: 20px;
  }

  .button-save {
    width: 170px;
    background: #ff6609;
    height: 32px;
    color: #ffffff;
    border-radius: 24px;
  }
}

.info-class-delete {
  position: absolute;
  left: 0;
  bottom: 33px;

  .v-btn {
    font-size: 12px;
    color: #a0a3bd;
    background: #ffffff;
  }
}
</style>
<style lang="scss">
.tab-item {
  .v-tabs-bar__content {
    justify-content: space-around !important;
  }
}
.pick-odd {
  width: 100%;
  .v-picker__body {
    width: 366px;
  }
}

.schedule-filter {
  .v-text-field {
    padding-top: 0px;
    margin-top: 0px;
  }

  .theme--light.v-text-field > .v-input__control > .v-input__slot:before {
    border-color: #d2d2d2;
    border: none;
  }

  input#nameHomework {
    height: 36px;
    width: 519px;
    max-height: 36px;
    left: 458px;
    top: 156px;
    border-radius: 4px;
    // border: 1px solid #cbd4db;
    padding-left: 10px;
  }

  .theme--light.v-text-field--outlined:not(.v-input--is-focused):not(.v-input--has-state)
    > .v-input__control
    > .v-input__slot
    fieldset {
    color: #cbd4db;
  }
}
</style>

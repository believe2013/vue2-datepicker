<template>
    <div class="box">
        <!--<section>
            <p>Marked Dates</p>
            <date-picker
                    v-model="value1"
                    format="YYYY-MM-DD"
                    type="date"
                    placeholder="Select date"
                    :is-marked="true"
                    :marked-dates="markedDates"
            >
                <template v-slot:cell="{cell, date}">
                    <div :style="styleCell(cell, date)">{{ cell.text }}</div>
                </template>
            </date-picker>
        </section>-->
        <section>
            <p>Marked Dates Range</p>
            <date-picker
                    v-model="value1"
                    format="YYYY-MM-DD"
                    type="date"
                    :range="true"
                    placeholder="Select date"
                    :is-marked="true"
                    :marked-dates="markedDates"
            >
                <template v-slot:cell="{cell, date}">
                    <div :style="styleCell(cell, date)">{{ cell.text }}</div>
                </template>
            </date-picker>
        </section>
    </div>
</template>


<script>
  export default {
    name: 'Marked',
    data() {
      return {
        value1: [],
        markedDates: [
          {
            date: "2020-07-26",
            marker: {
                color: "#B0BEC5",
                display_name: "Regular",
                id: 2,
                name: "regular",
                rate_plus: 23,
                sort: 2
            },
          }
        ]
      };
    },
    methods: {
      styleCell(cell, date) {

        const markedDate = this.markedDates[0]
        const styleObj = {}

        if (markedDate.date === date) {
          styleObj.backgroundColor = markedDate.marker.color
        }
        // styleObj.backgroundColor = markedDate.color

        // console.log(styleObj)
        return styleObj
      }
    }
  };
</script>


<style scoped>

</style>
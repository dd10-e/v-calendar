<template>
  <div class="example">
    <v-date-picker v-model="date" mode="dateTime" is24hr :available-times="availableTimes" 
      :available-dates='disabledDates'
    >
      <template v-slot="{ inputValue, inputEvents }">
        <input
          class="px-2 py-1 border rounded focus:outline-none focus:border-blue-300"
          :value="inputValue"
          v-on="inputEvents"
        />
      </template>
    </v-date-picker>
  </div>
</template>

<script>
export default {
  data() {
    return {
      date: new Date(),
      availableTimes: {
        options12: [
          { value: 0, label: '00' },
          { value: 1, label: '01' },
          { value: 2, label: '02' },
        ],
        options24: [
          { value: 0, label: '00' },
          { value: 1, label: '01' },
          { value: 2, label: '02' },
        ]
      },
      disabledDates: {
        start: new Date(),
        weekdays: [2, 3, 4, 5, 6, 7]
      }
    };
  },
  methods: {
    getYesterday() {
      const d = new Date();
      console.log(d.getDay())
      if (d.getDay() === 3) {
        return d
      }

    }
  }
};
</script>

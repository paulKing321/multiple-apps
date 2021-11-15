<template>
  <div class="m-auto font-bold" style="justify-content: center">
    <h1 class="text-2xl text-center my-2 font-bold">CALENDAR APP</h1>
    <section class="flex mx-2 justify-between text-red-500">
      <h2 class="font-bold text-left">{{ currentMonthName }}</h2>
      <h2 class="font-bold">{{ currentYear }}</h2>
    </section>
    <section class="flex my-2">
      <p class="m-2 text-center" style="width: 14.28%" 
      v-for="day in days" :key="day">{{ day }}</p>
    </section>
    <section class="flex flex-wrap">
      <p  class=" h-10 text-center" 
      style="width: 14.28%" 
      v-for="num in startDay()" 
      :key="num"></p>

      <p  class=" h-10 text-center" 
      style="width: 14.28%" 
      v-for="num in daysInMonth()" 
      :key="num"
      :class="currentDateClass(num)"
      >
      {{ num }}
      </p>
    </section>

    <section class="flex justify-between my-4">
      <button class="px-2 border rounded bg-gray-400" @click="prev">Prev</button>
      <button class="px-2 border rounded bg-gray-400 text-white" @click="next">Next</button>
    </section>
  </div> 
</template>

<script>
export default {
name: 'calendar',

  data () {
    return {
      currentDate: new Date().getUTCDate(),
      currentMonth: new Date().getMonth(),
      currentYear: new Date().getFullYear(),
      days: ['Sun', 'Mon', 'Tue', 'Wed', 'Thu', 'Fri', 'Sat']
    }
  },

  methods: {
    daysInMonth() {
      return new Date(this.currentYear, this.currentMonth +1, 0).getDate();
    },

    startDay() {
      return new Date(this.currentYear, this.currentMonth, 1).getDay();
      },

    next() {
      if(this.currentMonth === 11) {
        this.currentMonth = 0;
        this.currentYear++;
      } else {
        this.currentMonth++;
        }
    },

    prev() {
      if(this.currentMonth === 0) {
        this.currentMonth = 11;
        this.currentYear--;
      }else {
      this.currentMonth--;
    }
    },

    currentDateClass(num) {
      const calenderFullDate = new Date(this.currentYear, this.currentMonth, num).toDateString()
      const currentFullDate = new Date().toDateString()
      return calenderFullDate === currentFullDate ? 'text-yellow-600' : '';
      return new Date(this.currentYear, this.currentMonth, num) === new Date();
    }
  },

  computed: {
    currentMonthName(){
      return new Date(this.currentYear, this.currentMonth).toLocaleString("default", { month: "long" });
    },
  }
}
</script>

<style>

</style>
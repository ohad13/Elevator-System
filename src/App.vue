<script setup>
import { RouterLink, RouterView } from 'vue-router'
</script>

<template>
  <div class="elevator-system">
    <h4>Elevator Exercise</h4>
    <table>
      <tbody>
        <tr v-for="(row, rowIndex) in rows" :key="rowIndex" :id="rowIndex">
          <td style="width: 200px; border: gray; background-color: #ddd; text-align:right;"> {{ row.column1 }} </td>

          <td :id="'0' + rowIndex" class="elvCol" v-if="this.elevators[0].currentFloor == this.num - rowIndex">
            <svg class="svgClass1" id="elev-1" xmlns="http://www.w3.org/2000/svg" width="50" height="30"
              viewBox="0 0 50 50" fill="#00000">
              <path id="path1"
                d="M 15.875 0 C 15.617188 0.0351563 15.378906 0.167969 15.21875 0.375 L 10.21875 6.375 C 9.976563 6.675781 9.929688 7.085938 10.097656 7.433594 C 10.265625 7.78125 10.617188 8 11 8 L 21 8 C 21.382813 8 21.734375 7.78125 21.902344 7.433594 C 22.070313 7.085938 22.023438 6.675781 21.78125 6.375 L 16.78125 0.375 C 16.566406 0.101563 16.222656 -0.0429688 15.875 0 Z M 29.8125 0 C 29.460938 0.0625 29.171875 0.308594 29.046875 0.640625 C 28.925781 0.976563 28.992188 1.351563 29.21875 1.625 L 34.21875 7.625 C 34.410156 7.863281 34.695313 8 35 8 C 35.304688 8 35.589844 7.863281 35.78125 7.625 L 40.78125 1.625 C 41.023438 1.324219 41.070313 0.914063 40.902344 0.566406 C 40.734375 0.21875 40.382813 0 40 0 L 30 0 C 29.96875 0 29.9375 0 29.90625 0 C 29.875 0 29.84375 0 29.8125 0 Z M 32.125 2 L 37.875 2 L 35 5.4375 Z M 16 2.5625 L 18.875 6 L 13.125 6 Z M 3 10 C 1.355469 10 0 11.355469 0 13 L 0 47 C 0 48.644531 1.355469 50 3 50 L 47 50 C 48.644531 50 50 48.644531 50 47 L 50 13 C 50 11.355469 48.644531 10 47 10 Z M 3 12 L 47 12 C 47.554688 12 48 12.445313 48 13 L 48 47 C 48 47.554688 47.554688 48 47 48 L 3 48 C 2.445313 48 2 47.554688 2 47 L 2 13 C 2 12.445313 2.445313 12 3 12 Z M 11 14 C 8.800781 14 7 15.800781 7 18 C 7 20.199219 8.800781 22 11 22 C 13.199219 22 15 20.199219 15 18 C 15 15.800781 13.199219 14 11 14 Z M 11 22 C 7.675781 22 5 24.675781 5 28 L 5 35 C 4.996094 35.386719 5.214844 35.738281 5.5625 35.90625 L 7 36.625 L 7 45 C 7 45.550781 7.449219 46 8 46 L 14 46 C 14.550781 46 15 45.550781 15 45 L 15 36.625 L 16.4375 35.90625 C 16.785156 35.738281 17.003906 35.386719 17 35 L 17 28 C 17 24.675781 14.324219 22 11 22 Z M 25 14 C 22.800781 14 21 15.800781 21 18 C 21 20.199219 22.800781 22 25 22 C 27.199219 22 29 20.199219 29 18 C 29 15.800781 27.199219 14 25 14 Z M 25 22 C 21.675781 22 19 24.675781 19 28 L 19 35 C 18.996094 35.386719 19.214844 35.738281 19.5625 35.90625 L 21 36.625 L 21 45 C 21 45.550781 21.449219 46 22 46 L 28 46 C 28.550781 46 29 45.550781 29 45 L 29 36.625 L 30.4375 35.90625 C 30.785156 35.738281 31.003906 35.386719 31 35 L 31 28 C 31 24.675781 28.324219 22 25 22 Z M 39 14 C 36.800781 14 35 15.800781 35 18 C 35 20.199219 36.800781 22 39 22 C 41.199219 22 43 20.199219 43 18 C 43 15.800781 41.199219 14 39 14 Z M 39 22 C 35.675781 22 33 24.675781 33 28 L 33 35 C 32.996094 35.386719 33.214844 35.738281 33.5625 35.90625 L 35 36.625 L 35 45 C 35 45.550781 35.449219 46 36 46 L 42 46 C 42.550781 46 43 45.550781 43 45 L 43 36.625 L 44.4375 35.90625 C 44.785156 35.738281 45.003906 35.386719 45 35 L 45 28 C 45 24.675781 42.324219 22 39 22 Z M 11 16 C 12.117188 16 13 16.882813 13 18 C 13 19.117188 12.117188 20 11 20 C 9.882813 20 9 19.117188 9 18 C 9 16.882813 9.882813 16 11 16 Z M 25 16 C 26.117188 16 27 16.882813 27 18 C 27 19.117188 26.117188 20 25 20 C 23.882813 20 23 19.117188 23 18 C 23 16.882813 23.882813 16 25 16 Z M 39 16 C 40.117188 16 41 16.882813 41 18 C 41 19.117188 40.117188 20 39 20 C 37.882813 20 37 19.117188 37 18 C 37 16.882813 37.882813 16 39 16 Z M 11 24 C 13.277344 24 15 25.722656 15 28 L 15 34.375 L 13.5625 35.09375 C 13.214844 35.261719 12.996094 35.613281 13 36 L 13 44 L 9 44 L 9 36 C 9.003906 35.613281 8.785156 35.261719 8.4375 35.09375 L 7 34.375 L 7 28 C 7 25.722656 8.722656 24 11 24 Z M 25 24 C 27.277344 24 29 25.722656 29 28 L 29 34.375 L 27.5625 35.09375 C 27.214844 35.261719 26.996094 35.613281 27 36 L 27 44 L 23 44 L 23 36 C 23.003906 35.613281 22.785156 35.261719 22.4375 35.09375 L 21 34.375 L 21 28 C 21 25.722656 22.722656 24 25 24 Z M 39 24 C 41.277344 24 43 25.722656 43 28 L 43 34.375 L 41.5625 35.09375 C 41.214844 35.261719 40.996094 35.613281 41 36 L 41 44 L 37 44 L 37 36 C 37.003906 35.613281 36.785156 35.261719 36.4375 35.09375 L 35 34.375 L 35 28 C 35 25.722656 36.722656 24 39 24 Z"
                fill="#000000" />
            </svg>
          </td>

          <td :id="'0' + rowIndex" class="elvCol"
            v-else-if="this.num - rowIndex == elevators[0].targetFloor && elevators[0].timerValue != 0">
            {{ this.elevators[0].timerValue }} sec</td>
          <td :id="'0' + rowIndex" class="elvCol" v-else>{{ row.column2 }}</td>

          <td :id="'1' + rowIndex" class="elvCol" v-if="this.elevators[1].currentFloor == this.num - rowIndex">
            <svg class="svgClass2" id="elev-2" xmlns="http://www.w3.org/2000/svg" width="50" height="30"
              viewBox="0 0 50 50" fill="#00000">
              <path id="path2"
                d="M 15.875 0 C 15.617188 0.0351563 15.378906 0.167969 15.21875 0.375 L 10.21875 6.375 C 9.976563 6.675781 9.929688 7.085938 10.097656 7.433594 C 10.265625 7.78125 10.617188 8 11 8 L 21 8 C 21.382813 8 21.734375 7.78125 21.902344 7.433594 C 22.070313 7.085938 22.023438 6.675781 21.78125 6.375 L 16.78125 0.375 C 16.566406 0.101563 16.222656 -0.0429688 15.875 0 Z M 29.8125 0 C 29.460938 0.0625 29.171875 0.308594 29.046875 0.640625 C 28.925781 0.976563 28.992188 1.351563 29.21875 1.625 L 34.21875 7.625 C 34.410156 7.863281 34.695313 8 35 8 C 35.304688 8 35.589844 7.863281 35.78125 7.625 L 40.78125 1.625 C 41.023438 1.324219 41.070313 0.914063 40.902344 0.566406 C 40.734375 0.21875 40.382813 0 40 0 L 30 0 C 29.96875 0 29.9375 0 29.90625 0 C 29.875 0 29.84375 0 29.8125 0 Z M 32.125 2 L 37.875 2 L 35 5.4375 Z M 16 2.5625 L 18.875 6 L 13.125 6 Z M 3 10 C 1.355469 10 0 11.355469 0 13 L 0 47 C 0 48.644531 1.355469 50 3 50 L 47 50 C 48.644531 50 50 48.644531 50 47 L 50 13 C 50 11.355469 48.644531 10 47 10 Z M 3 12 L 47 12 C 47.554688 12 48 12.445313 48 13 L 48 47 C 48 47.554688 47.554688 48 47 48 L 3 48 C 2.445313 48 2 47.554688 2 47 L 2 13 C 2 12.445313 2.445313 12 3 12 Z M 11 14 C 8.800781 14 7 15.800781 7 18 C 7 20.199219 8.800781 22 11 22 C 13.199219 22 15 20.199219 15 18 C 15 15.800781 13.199219 14 11 14 Z M 11 22 C 7.675781 22 5 24.675781 5 28 L 5 35 C 4.996094 35.386719 5.214844 35.738281 5.5625 35.90625 L 7 36.625 L 7 45 C 7 45.550781 7.449219 46 8 46 L 14 46 C 14.550781 46 15 45.550781 15 45 L 15 36.625 L 16.4375 35.90625 C 16.785156 35.738281 17.003906 35.386719 17 35 L 17 28 C 17 24.675781 14.324219 22 11 22 Z M 25 14 C 22.800781 14 21 15.800781 21 18 C 21 20.199219 22.800781 22 25 22 C 27.199219 22 29 20.199219 29 18 C 29 15.800781 27.199219 14 25 14 Z M 25 22 C 21.675781 22 19 24.675781 19 28 L 19 35 C 18.996094 35.386719 19.214844 35.738281 19.5625 35.90625 L 21 36.625 L 21 45 C 21 45.550781 21.449219 46 22 46 L 28 46 C 28.550781 46 29 45.550781 29 45 L 29 36.625 L 30.4375 35.90625 C 30.785156 35.738281 31.003906 35.386719 31 35 L 31 28 C 31 24.675781 28.324219 22 25 22 Z M 39 14 C 36.800781 14 35 15.800781 35 18 C 35 20.199219 36.800781 22 39 22 C 41.199219 22 43 20.199219 43 18 C 43 15.800781 41.199219 14 39 14 Z M 39 22 C 35.675781 22 33 24.675781 33 28 L 33 35 C 32.996094 35.386719 33.214844 35.738281 33.5625 35.90625 L 35 36.625 L 35 45 C 35 45.550781 35.449219 46 36 46 L 42 46 C 42.550781 46 43 45.550781 43 45 L 43 36.625 L 44.4375 35.90625 C 44.785156 35.738281 45.003906 35.386719 45 35 L 45 28 C 45 24.675781 42.324219 22 39 22 Z M 11 16 C 12.117188 16 13 16.882813 13 18 C 13 19.117188 12.117188 20 11 20 C 9.882813 20 9 19.117188 9 18 C 9 16.882813 9.882813 16 11 16 Z M 25 16 C 26.117188 16 27 16.882813 27 18 C 27 19.117188 26.117188 20 25 20 C 23.882813 20 23 19.117188 23 18 C 23 16.882813 23.882813 16 25 16 Z M 39 16 C 40.117188 16 41 16.882813 41 18 C 41 19.117188 40.117188 20 39 20 C 37.882813 20 37 19.117188 37 18 C 37 16.882813 37.882813 16 39 16 Z M 11 24 C 13.277344 24 15 25.722656 15 28 L 15 34.375 L 13.5625 35.09375 C 13.214844 35.261719 12.996094 35.613281 13 36 L 13 44 L 9 44 L 9 36 C 9.003906 35.613281 8.785156 35.261719 8.4375 35.09375 L 7 34.375 L 7 28 C 7 25.722656 8.722656 24 11 24 Z M 25 24 C 27.277344 24 29 25.722656 29 28 L 29 34.375 L 27.5625 35.09375 C 27.214844 35.261719 26.996094 35.613281 27 36 L 27 44 L 23 44 L 23 36 C 23.003906 35.613281 22.785156 35.261719 22.4375 35.09375 L 21 34.375 L 21 28 C 21 25.722656 22.722656 24 25 24 Z M 39 24 C 41.277344 24 43 25.722656 43 28 L 43 34.375 L 41.5625 35.09375 C 41.214844 35.261719 40.996094 35.613281 41 36 L 41 44 L 37 44 L 37 36 C 37.003906 35.613281 36.785156 35.261719 36.4375 35.09375 L 35 34.375 L 35 28 C 35 25.722656 36.722656 24 39 24 Z"
                fill="#000000" />
            </svg>
          </td>

          <td :id="'1' + rowIndex" class="elvCol"
            v-else-if="this.num - rowIndex == elevators[1].targetFloor && elevators[1].timerValue != 0">
            {{ this.elevators[1].timerValue }} sec</td>
          <td :id="'1' + rowIndex" class="elvCol" v-else>{{ row.column3 }}</td>

          <td :id="'2' + rowIndex" class="elvCol" v-if="this.elevators[2].currentFloor == this.num - rowIndex">
            <svg class="svgClass3" id="elev-3" xmlns="http://www.w3.org/2000/svg" width="50" height="30"
              viewBox="0 0 50 50" fill="#00000">
              <path id="path3"
                d="M 15.875 0 C 15.617188 0.0351563 15.378906 0.167969 15.21875 0.375 L 10.21875 6.375 C 9.976563 6.675781 9.929688 7.085938 10.097656 7.433594 C 10.265625 7.78125 10.617188 8 11 8 L 21 8 C 21.382813 8 21.734375 7.78125 21.902344 7.433594 C 22.070313 7.085938 22.023438 6.675781 21.78125 6.375 L 16.78125 0.375 C 16.566406 0.101563 16.222656 -0.0429688 15.875 0 Z M 29.8125 0 C 29.460938 0.0625 29.171875 0.308594 29.046875 0.640625 C 28.925781 0.976563 28.992188 1.351563 29.21875 1.625 L 34.21875 7.625 C 34.410156 7.863281 34.695313 8 35 8 C 35.304688 8 35.589844 7.863281 35.78125 7.625 L 40.78125 1.625 C 41.023438 1.324219 41.070313 0.914063 40.902344 0.566406 C 40.734375 0.21875 40.382813 0 40 0 L 30 0 C 29.96875 0 29.9375 0 29.90625 0 C 29.875 0 29.84375 0 29.8125 0 Z M 32.125 2 L 37.875 2 L 35 5.4375 Z M 16 2.5625 L 18.875 6 L 13.125 6 Z M 3 10 C 1.355469 10 0 11.355469 0 13 L 0 47 C 0 48.644531 1.355469 50 3 50 L 47 50 C 48.644531 50 50 48.644531 50 47 L 50 13 C 50 11.355469 48.644531 10 47 10 Z M 3 12 L 47 12 C 47.554688 12 48 12.445313 48 13 L 48 47 C 48 47.554688 47.554688 48 47 48 L 3 48 C 2.445313 48 2 47.554688 2 47 L 2 13 C 2 12.445313 2.445313 12 3 12 Z M 11 14 C 8.800781 14 7 15.800781 7 18 C 7 20.199219 8.800781 22 11 22 C 13.199219 22 15 20.199219 15 18 C 15 15.800781 13.199219 14 11 14 Z M 11 22 C 7.675781 22 5 24.675781 5 28 L 5 35 C 4.996094 35.386719 5.214844 35.738281 5.5625 35.90625 L 7 36.625 L 7 45 C 7 45.550781 7.449219 46 8 46 L 14 46 C 14.550781 46 15 45.550781 15 45 L 15 36.625 L 16.4375 35.90625 C 16.785156 35.738281 17.003906 35.386719 17 35 L 17 28 C 17 24.675781 14.324219 22 11 22 Z M 25 14 C 22.800781 14 21 15.800781 21 18 C 21 20.199219 22.800781 22 25 22 C 27.199219 22 29 20.199219 29 18 C 29 15.800781 27.199219 14 25 14 Z M 25 22 C 21.675781 22 19 24.675781 19 28 L 19 35 C 18.996094 35.386719 19.214844 35.738281 19.5625 35.90625 L 21 36.625 L 21 45 C 21 45.550781 21.449219 46 22 46 L 28 46 C 28.550781 46 29 45.550781 29 45 L 29 36.625 L 30.4375 35.90625 C 30.785156 35.738281 31.003906 35.386719 31 35 L 31 28 C 31 24.675781 28.324219 22 25 22 Z M 39 14 C 36.800781 14 35 15.800781 35 18 C 35 20.199219 36.800781 22 39 22 C 41.199219 22 43 20.199219 43 18 C 43 15.800781 41.199219 14 39 14 Z M 39 22 C 35.675781 22 33 24.675781 33 28 L 33 35 C 32.996094 35.386719 33.214844 35.738281 33.5625 35.90625 L 35 36.625 L 35 45 C 35 45.550781 35.449219 46 36 46 L 42 46 C 42.550781 46 43 45.550781 43 45 L 43 36.625 L 44.4375 35.90625 C 44.785156 35.738281 45.003906 35.386719 45 35 L 45 28 C 45 24.675781 42.324219 22 39 22 Z M 11 16 C 12.117188 16 13 16.882813 13 18 C 13 19.117188 12.117188 20 11 20 C 9.882813 20 9 19.117188 9 18 C 9 16.882813 9.882813 16 11 16 Z M 25 16 C 26.117188 16 27 16.882813 27 18 C 27 19.117188 26.117188 20 25 20 C 23.882813 20 23 19.117188 23 18 C 23 16.882813 23.882813 16 25 16 Z M 39 16 C 40.117188 16 41 16.882813 41 18 C 41 19.117188 40.117188 20 39 20 C 37.882813 20 37 19.117188 37 18 C 37 16.882813 37.882813 16 39 16 Z M 11 24 C 13.277344 24 15 25.722656 15 28 L 15 34.375 L 13.5625 35.09375 C 13.214844 35.261719 12.996094 35.613281 13 36 L 13 44 L 9 44 L 9 36 C 9.003906 35.613281 8.785156 35.261719 8.4375 35.09375 L 7 34.375 L 7 28 C 7 25.722656 8.722656 24 11 24 Z M 25 24 C 27.277344 24 29 25.722656 29 28 L 29 34.375 L 27.5625 35.09375 C 27.214844 35.261719 26.996094 35.613281 27 36 L 27 44 L 23 44 L 23 36 C 23.003906 35.613281 22.785156 35.261719 22.4375 35.09375 L 21 34.375 L 21 28 C 21 25.722656 22.722656 24 25 24 Z M 39 24 C 41.277344 24 43 25.722656 43 28 L 43 34.375 L 41.5625 35.09375 C 41.214844 35.261719 40.996094 35.613281 41 36 L 41 44 L 37 44 L 37 36 C 37.003906 35.613281 36.785156 35.261719 36.4375 35.09375 L 35 34.375 L 35 28 C 35 25.722656 36.722656 24 39 24 Z"
                fill="#000000" />
            </svg>
          </td>

          <td :id="'2' + rowIndex" class="elvCol"
            v-else-if="this.num - rowIndex == elevators[2].targetFloor && elevators[2].timerValue != 0">
            {{ this.elevators[2].timerValue }} sec</td>
          <td :id="'2' + rowIndex" class="elvCol" v-else>{{ row.column4 }}</td>

          <td :id="'3' + rowIndex" class="elvCol" v-if="this.elevators[3].currentFloor == this.num - rowIndex">
            <svg class="svgClass4" id="elev-4" xmlns="http://www.w3.org/2000/svg" width="50" height="30"
              viewBox="0 0 50 50" fill="#00000">
              <path id="path4"
                d="M 15.875 0 C 15.617188 0.0351563 15.378906 0.167969 15.21875 0.375 L 10.21875 6.375 C 9.976563 6.675781 9.929688 7.085938 10.097656 7.433594 C 10.265625 7.78125 10.617188 8 11 8 L 21 8 C 21.382813 8 21.734375 7.78125 21.902344 7.433594 C 22.070313 7.085938 22.023438 6.675781 21.78125 6.375 L 16.78125 0.375 C 16.566406 0.101563 16.222656 -0.0429688 15.875 0 Z M 29.8125 0 C 29.460938 0.0625 29.171875 0.308594 29.046875 0.640625 C 28.925781 0.976563 28.992188 1.351563 29.21875 1.625 L 34.21875 7.625 C 34.410156 7.863281 34.695313 8 35 8 C 35.304688 8 35.589844 7.863281 35.78125 7.625 L 40.78125 1.625 C 41.023438 1.324219 41.070313 0.914063 40.902344 0.566406 C 40.734375 0.21875 40.382813 0 40 0 L 30 0 C 29.96875 0 29.9375 0 29.90625 0 C 29.875 0 29.84375 0 29.8125 0 Z M 32.125 2 L 37.875 2 L 35 5.4375 Z M 16 2.5625 L 18.875 6 L 13.125 6 Z M 3 10 C 1.355469 10 0 11.355469 0 13 L 0 47 C 0 48.644531 1.355469 50 3 50 L 47 50 C 48.644531 50 50 48.644531 50 47 L 50 13 C 50 11.355469 48.644531 10 47 10 Z M 3 12 L 47 12 C 47.554688 12 48 12.445313 48 13 L 48 47 C 48 47.554688 47.554688 48 47 48 L 3 48 C 2.445313 48 2 47.554688 2 47 L 2 13 C 2 12.445313 2.445313 12 3 12 Z M 11 14 C 8.800781 14 7 15.800781 7 18 C 7 20.199219 8.800781 22 11 22 C 13.199219 22 15 20.199219 15 18 C 15 15.800781 13.199219 14 11 14 Z M 11 22 C 7.675781 22 5 24.675781 5 28 L 5 35 C 4.996094 35.386719 5.214844 35.738281 5.5625 35.90625 L 7 36.625 L 7 45 C 7 45.550781 7.449219 46 8 46 L 14 46 C 14.550781 46 15 45.550781 15 45 L 15 36.625 L 16.4375 35.90625 C 16.785156 35.738281 17.003906 35.386719 17 35 L 17 28 C 17 24.675781 14.324219 22 11 22 Z M 25 14 C 22.800781 14 21 15.800781 21 18 C 21 20.199219 22.800781 22 25 22 C 27.199219 22 29 20.199219 29 18 C 29 15.800781 27.199219 14 25 14 Z M 25 22 C 21.675781 22 19 24.675781 19 28 L 19 35 C 18.996094 35.386719 19.214844 35.738281 19.5625 35.90625 L 21 36.625 L 21 45 C 21 45.550781 21.449219 46 22 46 L 28 46 C 28.550781 46 29 45.550781 29 45 L 29 36.625 L 30.4375 35.90625 C 30.785156 35.738281 31.003906 35.386719 31 35 L 31 28 C 31 24.675781 28.324219 22 25 22 Z M 39 14 C 36.800781 14 35 15.800781 35 18 C 35 20.199219 36.800781 22 39 22 C 41.199219 22 43 20.199219 43 18 C 43 15.800781 41.199219 14 39 14 Z M 39 22 C 35.675781 22 33 24.675781 33 28 L 33 35 C 32.996094 35.386719 33.214844 35.738281 33.5625 35.90625 L 35 36.625 L 35 45 C 35 45.550781 35.449219 46 36 46 L 42 46 C 42.550781 46 43 45.550781 43 45 L 43 36.625 L 44.4375 35.90625 C 44.785156 35.738281 45.003906 35.386719 45 35 L 45 28 C 45 24.675781 42.324219 22 39 22 Z M 11 16 C 12.117188 16 13 16.882813 13 18 C 13 19.117188 12.117188 20 11 20 C 9.882813 20 9 19.117188 9 18 C 9 16.882813 9.882813 16 11 16 Z M 25 16 C 26.117188 16 27 16.882813 27 18 C 27 19.117188 26.117188 20 25 20 C 23.882813 20 23 19.117188 23 18 C 23 16.882813 23.882813 16 25 16 Z M 39 16 C 40.117188 16 41 16.882813 41 18 C 41 19.117188 40.117188 20 39 20 C 37.882813 20 37 19.117188 37 18 C 37 16.882813 37.882813 16 39 16 Z M 11 24 C 13.277344 24 15 25.722656 15 28 L 15 34.375 L 13.5625 35.09375 C 13.214844 35.261719 12.996094 35.613281 13 36 L 13 44 L 9 44 L 9 36 C 9.003906 35.613281 8.785156 35.261719 8.4375 35.09375 L 7 34.375 L 7 28 C 7 25.722656 8.722656 24 11 24 Z M 25 24 C 27.277344 24 29 25.722656 29 28 L 29 34.375 L 27.5625 35.09375 C 27.214844 35.261719 26.996094 35.613281 27 36 L 27 44 L 23 44 L 23 36 C 23.003906 35.613281 22.785156 35.261719 22.4375 35.09375 L 21 34.375 L 21 28 C 21 25.722656 22.722656 24 25 24 Z M 39 24 C 41.277344 24 43 25.722656 43 28 L 43 34.375 L 41.5625 35.09375 C 41.214844 35.261719 40.996094 35.613281 41 36 L 41 44 L 37 44 L 37 36 C 37.003906 35.613281 36.785156 35.261719 36.4375 35.09375 L 35 34.375 L 35 28 C 35 25.722656 36.722656 24 39 24 Z"
                fill="#000000" />
            </svg>
          </td>
          
          <td :id="'3' + rowIndex" class="elvCol"
            v-else-if="this.num - rowIndex == elevators[3].targetFloor && elevators[3].timerValue != 0">
            {{ this.elevators[3].timerValue }} sec</td>
          <td :id="'3' + rowIndex" class="elvCol" v-else>{{ row.column5 }}</td>

          <td :id="'4' + rowIndex" class="elvCol" v-if="this.elevators[4].currentFloor == this.num - rowIndex">
            <svg class="svgClass5" id="elev-5" xmlns="http://www.w3.org/2000/svg" width="50" height="30"
              viewBox="0 0 50 50" fill="#00000">
              <path id="path5"
                d="M 15.875 0 C 15.617188 0.0351563 15.378906 0.167969 15.21875 0.375 L 10.21875 6.375 C 9.976563 6.675781 9.929688 7.085938 10.097656 7.433594 C 10.265625 7.78125 10.617188 8 11 8 L 21 8 C 21.382813 8 21.734375 7.78125 21.902344 7.433594 C 22.070313 7.085938 22.023438 6.675781 21.78125 6.375 L 16.78125 0.375 C 16.566406 0.101563 16.222656 -0.0429688 15.875 0 Z M 29.8125 0 C 29.460938 0.0625 29.171875 0.308594 29.046875 0.640625 C 28.925781 0.976563 28.992188 1.351563 29.21875 1.625 L 34.21875 7.625 C 34.410156 7.863281 34.695313 8 35 8 C 35.304688 8 35.589844 7.863281 35.78125 7.625 L 40.78125 1.625 C 41.023438 1.324219 41.070313 0.914063 40.902344 0.566406 C 40.734375 0.21875 40.382813 0 40 0 L 30 0 C 29.96875 0 29.9375 0 29.90625 0 C 29.875 0 29.84375 0 29.8125 0 Z M 32.125 2 L 37.875 2 L 35 5.4375 Z M 16 2.5625 L 18.875 6 L 13.125 6 Z M 3 10 C 1.355469 10 0 11.355469 0 13 L 0 47 C 0 48.644531 1.355469 50 3 50 L 47 50 C 48.644531 50 50 48.644531 50 47 L 50 13 C 50 11.355469 48.644531 10 47 10 Z M 3 12 L 47 12 C 47.554688 12 48 12.445313 48 13 L 48 47 C 48 47.554688 47.554688 48 47 48 L 3 48 C 2.445313 48 2 47.554688 2 47 L 2 13 C 2 12.445313 2.445313 12 3 12 Z M 11 14 C 8.800781 14 7 15.800781 7 18 C 7 20.199219 8.800781 22 11 22 C 13.199219 22 15 20.199219 15 18 C 15 15.800781 13.199219 14 11 14 Z M 11 22 C 7.675781 22 5 24.675781 5 28 L 5 35 C 4.996094 35.386719 5.214844 35.738281 5.5625 35.90625 L 7 36.625 L 7 45 C 7 45.550781 7.449219 46 8 46 L 14 46 C 14.550781 46 15 45.550781 15 45 L 15 36.625 L 16.4375 35.90625 C 16.785156 35.738281 17.003906 35.386719 17 35 L 17 28 C 17 24.675781 14.324219 22 11 22 Z M 25 14 C 22.800781 14 21 15.800781 21 18 C 21 20.199219 22.800781 22 25 22 C 27.199219 22 29 20.199219 29 18 C 29 15.800781 27.199219 14 25 14 Z M 25 22 C 21.675781 22 19 24.675781 19 28 L 19 35 C 18.996094 35.386719 19.214844 35.738281 19.5625 35.90625 L 21 36.625 L 21 45 C 21 45.550781 21.449219 46 22 46 L 28 46 C 28.550781 46 29 45.550781 29 45 L 29 36.625 L 30.4375 35.90625 C 30.785156 35.738281 31.003906 35.386719 31 35 L 31 28 C 31 24.675781 28.324219 22 25 22 Z M 39 14 C 36.800781 14 35 15.800781 35 18 C 35 20.199219 36.800781 22 39 22 C 41.199219 22 43 20.199219 43 18 C 43 15.800781 41.199219 14 39 14 Z M 39 22 C 35.675781 22 33 24.675781 33 28 L 33 35 C 32.996094 35.386719 33.214844 35.738281 33.5625 35.90625 L 35 36.625 L 35 45 C 35 45.550781 35.449219 46 36 46 L 42 46 C 42.550781 46 43 45.550781 43 45 L 43 36.625 L 44.4375 35.90625 C 44.785156 35.738281 45.003906 35.386719 45 35 L 45 28 C 45 24.675781 42.324219 22 39 22 Z M 11 16 C 12.117188 16 13 16.882813 13 18 C 13 19.117188 12.117188 20 11 20 C 9.882813 20 9 19.117188 9 18 C 9 16.882813 9.882813 16 11 16 Z M 25 16 C 26.117188 16 27 16.882813 27 18 C 27 19.117188 26.117188 20 25 20 C 23.882813 20 23 19.117188 23 18 C 23 16.882813 23.882813 16 25 16 Z M 39 16 C 40.117188 16 41 16.882813 41 18 C 41 19.117188 40.117188 20 39 20 C 37.882813 20 37 19.117188 37 18 C 37 16.882813 37.882813 16 39 16 Z M 11 24 C 13.277344 24 15 25.722656 15 28 L 15 34.375 L 13.5625 35.09375 C 13.214844 35.261719 12.996094 35.613281 13 36 L 13 44 L 9 44 L 9 36 C 9.003906 35.613281 8.785156 35.261719 8.4375 35.09375 L 7 34.375 L 7 28 C 7 25.722656 8.722656 24 11 24 Z M 25 24 C 27.277344 24 29 25.722656 29 28 L 29 34.375 L 27.5625 35.09375 C 27.214844 35.261719 26.996094 35.613281 27 36 L 27 44 L 23 44 L 23 36 C 23.003906 35.613281 22.785156 35.261719 22.4375 35.09375 L 21 34.375 L 21 28 C 21 25.722656 22.722656 24 25 24 Z M 39 24 C 41.277344 24 43 25.722656 43 28 L 43 34.375 L 41.5625 35.09375 C 41.214844 35.261719 40.996094 35.613281 41 36 L 41 44 L 37 44 L 37 36 C 37.003906 35.613281 36.785156 35.261719 36.4375 35.09375 L 35 34.375 L 35 28 C 35 25.722656 36.722656 24 39 24 Z"
                fill="#000000" />
            </svg>
          </td>

          <td :id="'4' + rowIndex" class="elvCol"
            v-else-if="this.num - rowIndex == elevators[4].targetFloor && elevators[4].timerValue != 0">
            {{ this.elevators[4].timerValue }} sec</td>
          <td :id="'4' + rowIndex" class="elvCol" v-else>{{ row.column6 }}</td>

          <td style=" border: gray; background-color: #ddd; ">
            <button style="width:60px" @click="callButtonClick(rowIndex)" :id="'button-' + rowIndex"
              :class="[row.elevatorState === 'Call' ? 'call-button' : (row.elevatorState === 'Waiting' ? 'waiting-button' : 'arrived-button')]"
              :disabled="row.elevatorState != 'Call'">{{ row.elevatorState }}
            </button>
          </td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
export default {
  data() {
    return {
      num: 10,
      rows: [],
      elevators: [
        {
          id: 0,
          taken: false,
          currentFloor: 1,
          targetFloor: null,
          doorOpen: false,
          buttons: [],
          timerValue: 0,
          timerInterval: null,
        }, {
          id: 1,
          taken: false,
          currentFloor: 1,
          targetFloor: null,
          doorOpen: false,
          buttons: [],
          timerValue: 0,
          timerInterval: null,
        }, {
          id: 2,
          taken: false,
          currentFloor: 1,
          targetFloor: null,
          doorOpen: false,
          buttons: [],
          timerValue: 0,
          timerInterval: null,
        }, {
          id: 3,
          taken: false,
          currentFloor: 1,
          targetFloor: null,
          doorOpen: false,
          buttons: [],
          timerValue: 0,
          timerInterval: null,
        }, {
          id: 4,
          taken: false,
          currentFloor: 1,
          targetFloor: null,
          doorOpen: false,
          buttons: [],
          timerValue: 0,
          timerInterval: null,
        },
      ]
    };
  },
  created() {
    this.elevators.forEach(elevator => {
      elevator.buttons = this.createButtonList(this.num);
    });
    this.rows = this.createRowsList(this.num);
  },
  methods: {
    startTimer(elevator) {
      // Set up a timer to update the timerValue property every second
      elevator.timerInterval = setInterval(() => {
        elevator.timerValue += 1;
      }, 1000);
    },
    createRowsList(count) {
      let rows = [];
      let floorName = ["9th", "8th", "7th", "6th", "5th", "4th", "3rd", "2nd", "1st", "Ground Floor"];
      for (let i = 0; i < count; i++) {
        rows.push({ column1: floorName[i], column2: '', column3: '', column4: '', column5: '', elevatorState: 'Call' });
      }
      return rows;
    },
    createButtonList(count) {
      let buttons = [];
      for (let i = count; i >= 1; i--) {
        buttons.push({ label: i.toString(), active: false });
      }
      this.waitList = [];
      return buttons;
    },
    calcNearestElev(buttonIndex) {
      buttonIndex = this.num - buttonIndex;
      let calc = Infinity;
      let indx = null;
      for (let index = 0; index < this.elevators.length; index++) {
        if (this.elevators[index].taken) continue;
        let cur = this.elevators[index].currentFloor;
        if (Math.abs(cur - buttonIndex) < calc) {
          calc = Math.abs(cur - buttonIndex);
          indx = index;
        }
      }
      return indx;
    },
    elevatorButtonClick(buttonIndex) {
      try {
        let elevatorIndex = this.calcNearestElev(buttonIndex);
        const elevator = this.elevators[elevatorIndex];
        let name = "path" + (elevatorIndex + 1);
        let svgClass = ".svgClass" + (elevatorIndex + 1);
        document.querySelector(svgClass).getElementById(name).setAttribute("fill", "red")
        this.startTimer(elevator);
        const targetFloor = elevator.buttons[buttonIndex].label;
        elevator.targetFloor = parseInt(targetFloor);
        this.moveElevator(elevatorIndex);
        const row = this.rows[buttonIndex];
        const diff = Math.abs(targetFloor - elevator.currentFloor);
        if (row.elevatorState === 'Call') {
          var button = document.getElementById("button-" + buttonIndex);
          button.style.backgroundColor = "red";
          button.style.color = "white";
          row.elevatorState = 'Waiting';
          // moving the elevator smoothly?
          setTimeout(() => {
            var button = document.getElementById("button-" + buttonIndex);
            button.style.backgroundColor = "transparent";
            button.style.color = "green";
            row.elevatorState = 'Arrived';
            clearInterval(elevator.timerInterval);// stops the timer from running.
            document.querySelector(svgClass).getElementById(name).setAttribute("fill", "green")
            elevator.timerInterval = null;
            elevator.timerValue = 0;
          }, diff * 2000);// the time it took 
          setTimeout(() => {
            row.elevatorState = 'Call';
            var button = document.getElementById("button-" + buttonIndex);
            button.style.backgroundColor = "green";
            button.style.color = "white";
            document.querySelector(svgClass).getElementById(name).setAttribute("fill", "black")
          }, diff * 2000 + 2000); // the time it took + 2 sec of waiting while "arrived".
        } else if (row.elevatorState === 'Waiting') {
          // do nothing - elevator is on the way somewhere
        } else {
          row.elevatorState = 'Call';
        }
      }
      catch (error) {
        console.log("bug in elevator Button Click ...", error);
      }
    },
    moveElevator(elevatorIndex) {
      const elevator = this.elevators[elevatorIndex];
      var audio = new Audio('/src/ding.mp3');
      console.log("move elevator number:", elevatorIndex, "to floor", elevator.targetFloor - 1);
      elevator.taken = true;
      const targetFloor = elevator.targetFloor;
      const currentFloor = elevator.currentFloor;
      const buttons = elevator.buttons;
      // Update button state
      buttons[targetFloor - 1].active = true;
      buttons[currentFloor - 1].active = false;
      const diff = Math.abs(targetFloor - elevator.currentFloor);
      // Open doors
      elevator.doorOpen = true;
      setTimeout(() => {
        // Close doors
        elevator.doorOpen = false;
        // Move elevator to target floor
        elevator.currentFloor = targetFloor;
        elevator.taken = false;
        audio.play();// ding sound
        console.log("Done move elevator number:", elevatorIndex, "to floor", elevator.targetFloor - 1);
      }, diff * 2000);
    },
    async delay(ms) {
      await new Promise(resolve => setTimeout(resolve, ms));
    },
    async callButtonClick(buttonIndex) {
      // get here after 'call' button was clicked!
      while (true) {
        // get the floor number (buttonIndex) and check if there is free elevator.
        let nearElevator = this.calcNearestElev(buttonIndex);
        // if there is one free - call the elevatorButtonClick function.
        if (nearElevator != null) {
          // console.log("there is a free elevator!"); 
          this.elevatorButtonClick(buttonIndex);
          break;
        }
        console.log("no free elevator");
        var button = document.getElementById("button-" + buttonIndex);
        button.style.backgroundColor = "yellow";
        button.disabled = "true";
        button.style.color = "white";
        // else (there is no free elevator) - stall time till there is free elevator.
        await this.delay(3000);// 3 sec
      }
    },
  }
};
</script>

<style scoped>
h4 {
  font-weight: bold;
  /* make the text bold */
  text-align: center;
  /* center the text horizontally */
}

button {
  background-color: green;
  color: #fff
}

table {
  width: auto;/*400px;*/
  /* set the width of the table */
  height: 200px;
  /* set the height of the table */
  border-collapse: collapse;
  /* collapse the border of the table */
  background-color: #fff;
}

th,td {
  /* width: 10px, */
  padding: 10px;
  /* set the padding of the cells */
  border: 1px solid rgb(173, 168, 168);
  /* set the border of the cells */
  height: 50px;
  width: 100px;
  text-align: center;
}

.elvCol {
  width: 800px;
  height: 68px;
}
</style>
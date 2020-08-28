<template>
  <div id="app">
    <section class="top-section">
      <div class="btn-grp">
        <button class="btn" @click="shuffleBox">Shuffle</button>
        <button class="btn" @click="sortBox">Sort</button>
      </div>
    </section>
    <section class="bottom-section">
      <div class="page-container">
        <div class="left-col">
          <div class="block-container">
            <div class="box" v-for="obj in numArr" :key="obj.number" :style="{ backgroundColor: `${obj.bgColor}` }">
              <div :class="`box-${obj.number}`">
                <span class="number">{{obj.number}}</span>
              </div>
            </div>
          </div>
        </div>
        <div class="right-col">
          <div class="btn-grp">
            <button class="btn" @click="shuffleBox">Shuffle</button>
            <button class="btn" @click="sortBox">Sort</button>
          </div>
        </div>
      </div>
    </section>
  </div>
</template>

<script>
  export default {
    name: 'app',
    data() {
      return {
        numArr: [
          {
            number: 1,
            bgColor: "#6f98a8",
          },
          {
            number: 2,
            bgColor: "#2b8ead",
          },
          {
            number: 3,
            bgColor: "#2f454e",
          },
          {
            number: 4,
            bgColor: "#2b8ead",
          },
          {
            number: 5,
            bgColor: "#2f454e",
          },
          {
            number: 6,
            bgColor: "#bfbfbf",
          },
          {
            number: 7,
            bgColor: "#bfbfbf",
          },
          {
            number: 8,
            bgColor: "#6f98a8",
          },
          {
            number: 9,
            bgColor: "#2f454e",
          }
        ]
      }
    },
    methods: {
      shuffleBox: function () {
        return this.numArr.sort(() => Math.random() - 0.5);
      },
      sortBox: function () {
        return this.numArr.sort((a, b) => a.number - b.number);
      }
    }
  }
</script>

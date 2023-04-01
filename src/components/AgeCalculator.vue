<script setup>
import { ref } from "vue";
</script>

<template>
  <main>
    <div class="main-container">
      <div class="input-container">
        <div>
          <label for="day">day</label>
          <input
            ref="day"
            v-model="day"
            type="number"
            name="day"
            placeholder="DD"
            @blur="day = day.padStart(2, 0)"
          />
        </div>

        <div>
          <label for="month">month</label>
          <input
            ref="month"
            v-model="month"
            type="number"
            name="month"
            placeholder="MM"
            @blur="month = month.padStart(2, 0)"
          />
        </div>

        <div>
          <label for="year">year</label>
          <input
            ref="year"
            v-model="year"
            type="number"
            placeholder="YYYY"
            name="year"
            @blur="year = year.padStart(4, 0)"
          />
        </div>
      </div>

      <!-- <img src="/icon-arrow.svg" alt="" /> -->
      <div class="output-container">
        <!-- <hr /> -->
        <h1>
          <span>{{ yearCalc || "38" }}</span> years
        </h1>
        <h2>
          <span>{{ monthCalc || "3" }}</span> months
        </h2>
        <h3>
          <span>{{ dayCalc || "26" }}</span> days
        </h3>
      </div>
    </div>
  </main>
</template>

<style scoped>
main {
  font-family: "Poppins", sans-serif;
  display: grid;
  place-content: center;
  min-height: 100vh;
  background-color: var(--off-white);
}
.main-container {
  background-color: var(--white);
  padding: 3rem 1rem;
  margin: 1rem;
  border-radius: 2rem 2rem 6rem 2rem;
  width: 100%;
}

.input-container {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  gap: 1rem;
  width: 100%;
}

label {
  text-transform: uppercase;
  letter-spacing: 0.15rem;
  font-size: 0.75rem;
  color: var(--smokey-grey);
}

input {
  width: 100%;
  /* padding: 0.5rem; */
}

h1,
h2,
h3 {
  font-size: 2rem;
  font-weight: 800;
  font-style: italic;
}
</style>

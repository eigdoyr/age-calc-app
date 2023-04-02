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

      <div class="divider">
        <img src="/icon-arrow.svg" alt="" />
      </div>
      <hr />
      <div class="output-container">
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
.main-container {
  background-color: var(--white);
  padding: 3rem 1.5rem;
  border-radius: 2rem 2rem 6rem 2rem;
  width: 100%;
  max-width: 52.25rem;
}

.input-container {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  gap: 1rem;
  width: 100%;
  /* max-width: 30rem; */
}

.divider {
  position: relative;
  display: flex;
  justify-content: center;
}

label {
  text-transform: uppercase;
  letter-spacing: 0.15rem;
  font-size: 0.75rem;
  color: var(--smokey-grey);
}

input {
  width: 100%;
  padding: 0.7rem;
  border-radius: 0.5rem;
  border: 1px solid var(--light-grey);
  color: var(--off-black);
  font-size: 1.15rem;
}

h1,
h2,
h3 {
  font-size: 3.5rem;
  font-weight: 800;
  font-style: italic;
  line-height: 3.65rem;
}

span {
  color: var(--purple);
}

hr {
  margin: 4.25rem 0;
  background-color: var(--light-grey);
  height: 1.5px;
  border: none;
}

img {
  background-color: var(--purple);
  border-radius: 50%;
  padding: 0.5rem;
  position: absolute;
  margin-top: 2.5rem;
}

@media (width>=1024px) {
  .main-container {
    padding: 3.8rem;
  }

  .input-container {
    width: 80%;
    gap: 2rem;
  }

  .divider {
    justify-content: flex-end;
  }

  label {
    letter-spacing: 0.15rem;
    font-size: 0.85rem;
  }

  input {
    border-radius: 0.5rem;
    font-size: 2rem;
    margin: 0.65rem 0;
  }

  h1,
  h2,
  h3 {
    font-size: 6.5rem;
    line-height: 6.85rem;
  }

  hr {
    margin: 2.25rem 0 2.75rem 0;
  }

  img {
    padding: 1.65rem;
    position: absolute;
    margin-top: -1rem;
  }
}
</style>

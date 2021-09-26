<template>
  <div>
    <select name="options" id="select" :class="selectedItem.class" @change="choose($event)">
      <option
        v-for="(item, index) in items"
        :value="index"
        :key="index"
        :class="item.class"
      >
        {{ item.text }}
      </option>
    </select>
  </div>
</template>

<script>
export default {
  name: "Select",
  data() {
    return {
      items: [
        { text: "ON", class: "orange" },
        { text: "OFF", class: "red" },
        { text: "AUTO", class: "green" },
      ],
      selectedItemIndex: 0,
    }
  },
  computed: {
    selectedItem() {
      return this.items[this.selectedItemIndex]
    },
  },
  methods: {
    choose(event) {
      this.selectedItemIndex = event.target.value;
    },
  },
}
</script>

<style>
#select {
  font-size: 26px;
  text-align: center;
  font-weight: 600;
  font-family: sans-serif;
  padding: 10px 10px;
  /* background-color: #fff; */
  border: none;
  border-radius: 10px;
  cursor: pointer;
  color: #fff;
}

.green {
  background-color: #26ae60;
}
.red {
  background-color: #eb5757;
}
.orange {
  background-color: #f6943d;
}
</style>

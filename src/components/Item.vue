<template>
  <div class="col-sm-4" @click="switchItem" title="Click to generate a new one">
    <div class="item-card">
      <div class="card-block">
        <h4 class="card-title">{{ item.name }}</h4>
        <div v-for="(value, key, index) in item" :key="key">
          <div v-if="index < 5">
            <strong>{{ key }}</strong
            >: {{ value }}
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ["passedItem", "type"],
  data() {
    return {
      item: {}
    };
  },
  methods: {
    switchItem() {
      let random_id = Math.floor(Math.random() * 63) + 1;
      fetch(
        `https://swapi.dev/api/${this.type}/${random_id}`,
        { method: "GET" },
        { mode: "cors" }
      )
        .then(response => response.json())
        .then(json => (this.item = json));
    }
  },
  created() {
    this.item = this.passedItem;
  }
};
</script>

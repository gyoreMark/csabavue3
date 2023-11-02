<template>
  <div class="background">
    <input
      class="form-control"
      type="text"
      placeholder="Növény helye"
      aria-label="default input example"
      id="novenyInput"
      v-model="novenyInput"
    />

    <button
      type="button"
      class="btn btn-secondary"
      id="addBtn"
      @click="addNoveny"
    >
      Hozzáadás
    </button>

    <ul class="list-group">
      <li
        class="list-group-item active"
        aria-current="true"
        v-for="(item, index) in items"
        :key="index"
      >
        {{ item }}
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  props: {
    msg: String,
  },

  data() {
    return {
      novenyInput: "",
      items: [],
    };
  },

  methods: {
    addNoveny() {
      if (this.novenyInput) {
        this.items.push(this.novenyInput);
        this.novenyInput = "";
      }
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.background {
  position: absolute;
  width: 100%;
  height: 100%;
  display: flex;
  flex-direction: column;
  justify-content: center;
  background-color: rgb(200, 141, 255);
  top: 0;
  left: 0;
}

#addBtn {
  margin-top: 20px;
  margin-bottom: 20px;
}
</style>

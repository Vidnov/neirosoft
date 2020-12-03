<template>
  <div class="diagramm-container container">
    <p>По департаментам</p>

    <div id="diagramma">
      <Diagramm
        v-bind:departments="departments_title"
        v-bind:employees="employees"
        v-bind:color="color"
      />
    </div>
  </div>
</template>

<script>
import Diagramm from "./Diagramm.vue";
export default {
  name: "Diagramm_block",
  data() {
    return {
      chartdata: null,
      color: [
        "#2B78FE",
        "#8295FA",
        "#FFBB49",
        "#87D227",
        "#20CBAC",
        "#01B0D7",
        "#6235B0",
        "#9559FF",
        "#C055D1",
        "#FF7979",
      ],
    };
  },
  components: {
    Diagramm,
  },

  mounted() {},
  props: ["departments_title", "employees"],
};
</script>

<style lang="scss" scoped>
#icon {
  position: relative;

  bottom: 310px;
  left: 224px;
}
#diagramma {
  display: grid;
  position: relative;
  
  border: 1px solid black;
  margin-left: 0;
  margin-top: 68px;
  padding: 0;
  height: 609px;
  width:1650px ;
}
.diagramm-content {
  margin-top: 50px;
  display: grid;
  grid-template-columns: 609px;
}
</style>

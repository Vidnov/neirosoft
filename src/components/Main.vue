<template>
  <div class="main">
    <div class="choise container">
      <div>
        <h2>{{ Statistic.total }}</h2>
        <span>Сотрудников в штате</span>
      </div>
      <div>
        <h2>{{ Statistic.males }}</h2>
        <span>Мужчины</span>
      </div>
      <div>
        <h2>{{ Statistic.females }}</h2>
        <span>Женщин</span>
      </div>
      <div>
        <h2>{{ Statistic.couples }}</h2>
        <span>Пар</span>
      </div>
    </div>
    <section>
      <DiagrammBlock
        v-if="loader"
        v-bind:employees="employees"
        v-bind:departments_title="departments_title"
      />
    </section>
  </div>
</template>

<script>
import DiagrammBlock from "./../components/Diagramm_block.vue";
import dataStatistic from "./../../test.json";

export default {
  name: "Header",
  components: {
    DiagrammBlock
  },
  data() {
    return {
      loader: false,
      Statistic: "",
      departments: [],
      employees: [],
      departments_title: [],
    };
  },
  async mounted() {
    this.loaded = false;
    try {
      this.Statistic = dataStatistic.data;
      this.departments = dataStatistic.data.departments;
      this.loader = true;
      this.employees = this.departments.map((item) => {
        return item.employees;
      });
      this.departments_title = this.departments.map((item) => {
        return item.title;
      });
    } catch {}
  },
  props: ["dataStatistic"],
};
</script>

<style lang="scss" scoped>
.main {
  margin-top: 33px;

  .choise {
    display: grid;
    grid-template-columns: 169px 169px 169px 169px;
    grid-gap: 116px;
    padding-bottom: 100px;

    div {
      justify-content: center;
      align-content: center;
      text-align: center;
      h2 {
        margin: 0;
        padding: 0;
        color: #2b78fe;
        font-style: normal;
        font-size: 80px;
        line-height: 94px;
      }
      span {
        display: block;
        height: 60px;
        width: 167px;
      }
    }
  }
}
</style>

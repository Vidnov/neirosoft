
<script>
import VueChartJs from "vue-chartjs";
//const { reactiveProp } = VueChartJs.mixins;
export default {
  name: "Diagramm",
  extends: VueChartJs.Doughnut,
  components: {},
 
  props: ["departments","employees","color"],

  mounted() {
    this.renderChart(
      {
       labels: '',
        datasets: [
          {
            label: this._props.employees,
            backgroundColor: this._props.color,
            data: this._props.employees,
          },
        ],
      },
      { responsive: true, maintainAspectRatio: true }
    );
  },
};
</script>

<style lang="scss" scoped>
</style>

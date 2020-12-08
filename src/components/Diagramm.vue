
<script>
import {Doughnut} from "vue-chartjs";
export default {
  name: "Diagramm",
  extends: Doughnut,
  components: {},
  data() {
    return {
      options: {
        responsive: true,
        maintainAspectRatio: false,
        tooltips: {
          mode: "point",
        },
        hover: { intersect: true },
        layout: {
          padding: {
            left: -200,
            right: 100,
            top: 0,
            bottom: 0,
          }
          
        },
        elements: {
          point: {
            radius: 3,
            pointStyle: "circle",
          },
        },
        title: {
          display: false,
          text: "По департаментам",
        },
        legend: {
          align: "center",
          position: "right",
          fullWidth: true,
          labels: {
            usePointStyle: true,
            boxWidth: 35,
            fontSize: 22,
            padding: 30,
          },
        },
      },
    };
  },

  props: ["departments", "employees", "color"],

  mounted() {
    this.renderChart(
      {
        labels: this._props.departments,
        datasets: [
          {
            label: this._props.departments,
            backgroundColor: this._props.color,
            data: this._props.employees,
            borderWidth: 0,
            cutoutPercentage: true,
          },
        ],
        options: {
          legend: {
            position: "right",
          },
        },
      },
      this.options
    );
  },
};
</script>

<style lang="scss" >

</style>

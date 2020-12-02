<script>
import VueChartJs from 'vue-chartjs';
export default {

  name: "Diagramm",
  extends: VueChartJs.Doughnut,
  components: {},
    mounted () {
    this.renderChart({
      labels: ['Январь', 'Февраль', 'Март', 'Апрель', 'Май', 'Июнь', 'Июль', 'Август', 'Сентябрь', 'Октябрь', 'Ноябрь', 'Декабрь'],
      datasets: [
        {
          label: 'Коммиты на GitHub',
          backgroundColor: ['#2B78FE','#8295FA'],
          data: [3, 54, 13, 22, 69, 5]
        }
      ]
    }, {responsive: true, maintainAspectRatio: false})
  }
};
</script>

<style lang="scss" scoped>

</style>

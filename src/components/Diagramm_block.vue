<template>
  <div class="diagramm-container container">
    <p>По департаментам</p>
    {{departments}}
    <div  class="diagramm-content">
        <div id='diagramma'>
          <Diagramm/>
        </div>
        <div class="sections">
            <ul>
                <li>Администрация</li>
                <li>Отдел обеспечения магического правопорядка</li>
                <li>Отдел магических происшествий и катастроф</li>
                <li>Отдел регулирования магических популяций</li>
                <li>Отдел международного магического сотрудничества</li>
                <li>Отдел магического транспорта</li>
                <li>Отдел магических игр и спорта</li>
                <li>Отдел тайн</li>
                <li>Орден Феникса</li>
                <li>Мракоборцы</li>
            </ul>
        </div>
    </div>
  </div>
</template>

<script>
import Diagramm from "./Diagramm.vue";
export default {
  name: "Diagramm_block",
  components: {
    Diagramm
  },
  mounted(){
    console.log(this._props.departments)
  },
  props:['departments']
};
</script>

<style lang="scss" scoped>
.diagramm-content{
    display: grid;
    grid-template-columns: 609px 609px ;
}
</style>

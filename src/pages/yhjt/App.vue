<template>
  <div id="app">
    <img src="../../img/thumb_yhjt@2x.png" style="width:100%">

    <div class="section">
        <div class="line"></div>
        <div class="tip">战斗规则</div>
    </div>
    <div class="desc">1、英雄的星级越高,能力和潜力越强。</div>
    <div class="desc">2、使用魔石召唤每满5次,必得一个4星英雄或5星英雄。</div>
    <div class="desc">3、玩家每日最多使用水晶召唤10次,使用魔石召唤250次。</div>
    <div class="desc">4、玩家每日有一次免费的魔石召唤机会和5次免费的水晶召唤机会(不计算召唤次数)。</div>
    <div class="desc">5、玩家每日有1次5折魔石召唤机会。</div>
    <div class="desc">6、上述折扣召唤机会不叠加不顺延。</div>
    <div class="desc">7、召唤次数的重置时间为每日2:00。</div>
  </div>
</template>

<script>
export default {
  data () {
    return {
    }
  },
  components: {},
  computed: {},
  mounted () {
    this.loadData()
  },
  methods: {
    loadData () {
    }
  }
}
</script>

<style scoped>
body, div, span, header, footer, nav, section, aside, article, ul, dl, dt, dd, li, a, p, h1, h2, h3, h4,h5, h6, i, b, textarea, button, input, select, figure, figcaption, {
    padding: 0;
    margin: 0;
    list-style: none;
    font-style: normal;
    text-decoration: none;
    border: none;
    font-weight: normal;
    font-family: "Microsoft Yahei";
    box-sizing: border-box;
    -webkit-tap-highlight-color:transparent;
    -webkit-font-smoothing: antialiased;
    &:hover{
        outline: none;
    }
}
html {
  font-size: 20px;
}
table { border-collapse: collapse; border-spacing: 0; }
td, th { padding: 0; }
.rank{text-align: center;margin-bottom: 10px;}
.rank table{margin:  0 4%;width: 92%;}
.rank th{font-weight: normal;color: #666; text-align: center;font-size: 0.75rem;line-height: 1.9rem;}
.rank td{padding: .4rem 0; color: #333;font-size: 0.7rem;}
.rank td:first-child{color: #333;font-size: 14px;}
.rank tr:nth-child(even) td{background: #edeef0;}

.section {
  margin-top: 1rem;
  margin-left: 0.6rem;
  margin-right: 0.6rem;
  display: flex;
  flex-direction: row;
}
.line {
  background-color: #e77e11;
  width: 0.2rem;
  height: 1rem;
}
.tip {
  font-size: 0.7rem;
  margin-left:0.4rem;
  color: #e77e11;
}
.desc {
  font-size: 0.7rem;
  color: #333;
  margin-top: 0.6rem;
  margin-left: 0.6rem;
  margin-right: 0.6rem;
}
.reward {
  margin-left: 0.6rem;
  margin-top: 0.8rem;
  margin-right: 0.6rem;
  margin-bottom: 0.03rem;
  display: flex;
  flex-direction: row;
}
.rewardimg {
  width: 2.5rem;
  height: 2.5rem;
}
.item {
  margin-left: 0.4rem;
  display: flex;
  flex-direction: column;
}
.itemtitle {
  font-size: 0.7rem;
  color: #333;
  margin-top: 0.25rem;
}
.itemdesc {
  font-size: 0.6rem;
  color: #999;
  margin-top: 0.4rem;
}
.ranklist {
  display: flex;
  flex-direction: row;
  align-items: center;
}
.rankleft {
  flex:1;
  text-align: center;
  font-size: 14px;
  color: #333;
}
.rankright {
  flex:1;
  display: flex;
  flex-direction: row;
  justify-content: center;
}
.rankicon {
  /*display: flex;
  flex-direction: column;*/
  position: relative;
}

</style>

<template>
  <div id="app">
    <img src="../../img/thumb_xzsl@2x.png" style="width:100%">
    <div class="section">
        <div class="line"></div>
        <div class="tip">试炼说明说明</div>
    </div>
    <div class="desc">需要多人协作才能挑战星座的守护者;每日凌晨2点可以重新获得2次挑战机会;挑战时,所有英雄属性修正战斗力相同!</div>
    <div class="section">
        <div class="line"></div>
        <div class="tip">开放时间</div>
    </div>
    <div class="desc">17:30 - 24:00</div>
    <div class="section">
        <div class="line"></div>
        <div class="tip">混沌奖励</div>
    </div>
    <div >
      <div class="reward" v-for="(item,key) in items" :key="key">
        <img class="rewardimg" :src="item.icon">
        <div class="item">
          <div class="itemtitle">{{item.name}}</div>
          <div class="itemdesc">{{item.description}}</div>
        </div>
      </div>
    </div>

    <div class="section">
        <div class="line"></div>
        <div class="tip">BOSS技能</div>
    </div>
    <div v-for="(item,key) in boss" :key="key" class="boss">
      <div class="bossname">{{item.name}}</div>
      <div v-for="(sub,subkey) in item.skill" :key="subkey" class="bossskill">
        <div class="skillname">{{sub.name}}</div>
        <div class="skilldesc">{{sub.description}}</div>
      </div>
    </div>

  </div>
</template>

<script>
export default {
  data () {
    return {
      boss: [],
      items: []
    }
  },
  components: {},
  computed: {},
  mounted () {
    this.loadData()
  },
  methods: {
    loadData () {
      this.boss = window.CosBox.getBossInfo()
      this.items = window.CosBox.getBossDrops()
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

.boss {
  display: flex;
  flex-direction: column;
  align-items: center;
}
.bossname {
  font-size: 16px;
  color: #e77e11;
  text-align: center;
  margin-top: 0.6rem;
}
.bossskill {
  display: flex;
  flex-direction: row;
  margin-left: 0.6rem;
  margin-right: 0.6rem;
  margin-top: 1.3rem;
}
.skillname {
  font-size: 14px;
  color: #e88c46;
}
.skilldesc {
  flex: 1;
  font-size: 14px;
  color: #333;
  margin-left: .4rem;
}

</style>

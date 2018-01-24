<template>
  <div id="app">
    <img src="../../img/thumb_hdyj@2x.png" style="width:100%">
    <div class="section">
        <div class="line"></div>
        <div class="tip">玩法说明</div>
    </div>
    <div class="desc">远古战场的祭坛依然散发着混沌能量,率先获得2000混沌资源的一方获得胜利,胜利的关键就是占领祭坛!</div>
    <div class="section">
        <div class="line"></div>
        <div class="tip">开放时间</div>
    </div>
    <div class="desc">12:00 - 14:30    17:30 - 24:00</div>
    <div class="section">
        <div class="line"></div>
        <div class="tip">混沌奖励</div>
    </div>
    <div >
      <div class="reward">
        <img class="rewardimg" src="../../img/award_hero_essence@2x.png">
        <div class="item">
          <div class="itemtitle">英雄精华</div>
          <div class="itemdesc">英雄分解可得,用于英雄技能升级。</div>
        </div>
      </div>
      <div class="reward">
        <img class="rewardimg" src="../../img/award_crystal@2x.png">
        <div class="item">
          <div class="itemtitle">水晶</div>
          <div class="itemdesc">参与冒险即可获得,可在冒险模式中进行消费。</div>
        </div>
      </div>
      <div class="reward">
        <img class="rewardimg" src="../../img/award_honor@2x.png">
        <div class="item">
          <div class="itemtitle">荣誉点</div>
          <div class="itemdesc">参与混沌遗迹即可获得,可以用于荣誉商店消费。</div>
        </div>
      </div>
    </div>

    <div class="section">
        <div class="line"></div>
        <div class="tip">军衔奖励</div>
    </div>
    <div class="ranklist" style="margin-top:30px;margin-bottom:9px;">
      <div class="rankright" style="color:#999;font-size:12px">军衔</div>
      <div class="rankleft" style="color:#999;font-size:12px">达成条件</div>
      <div class="rankleft" style="color:#999;font-size:12px">奖励</div>
      <div class="rankright" style="color:#999;font-size:12px">每周俸禄</div>
    </div>
    <div class="ranklist" style="height:56px;" v-for="(item,key) in datas" :key="key">
      <div class="rankright">{{item.name}}</div>
      <div class="rankleft">{{descRank(item)}}</div>
      <div class="rankleft">{{item.name}}</div>
      <div class="rankright">
        <div style="position:relative;width:32px; height:32px; border:1px solid #ccc; text-align:center;">
          <img src="../../img/weekly_salary_dimensity@2x.png" width="100%" height="100%">
          <span style="width:100%; height:12px; line-height:12px; position:absolute; bottom:0px; left:0px; right:0px; color:#fff;font-size:10px;text-align:center;">
            {{item.reward_num1}}
          </span>
        </div>
        <div style="position:relative;width:32px; height:32px; border:1px solid #ccc; text-align:center;">
          <img src="../../img/weekly_salary_crystal@2x.png" width="100%" height="100%">
          <span style="width:100%; height:12px; line-height:12px; position:absolute; bottom:0px; left:0px; right:0px; color:#fff;font-size:10px;text-align:center;">
            {{item.reward_num2}}
          </span>
        </div>
      </div>
    </div>

  </div>
</template>

<script>
export default {
  data () {
    return {
      datas: [
      ]
    }
  },
  components: {},
  computed: {},
  mounted () {
    this.loadData()
  },
  methods: {
    loadData () {
      this.datas = window.CosBox.getBattleRank()
    },
    descRank (item) {
      var str = ''
      if (item.feat_value !== '0') {
        str += item.feat_value + '军衔经验'
      }
      if (item.rank_value > 0) {
        str += '\n军衔帮前' + item.rank_value
      }
      return str
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

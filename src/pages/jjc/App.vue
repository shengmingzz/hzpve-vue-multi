<template>
  <div id="app">
    <img src="../../img/thumb_hdyj@2x.png" style="width:100%">
    <div class="section">
        <div class="line"></div>
        <div class="tip">奖励说明</div>
    </div>
    <div class="desc">1、您的竞技场历史最高排名为:10001,提高历史最高排名可获得大量奖励!</div>
    <div class="desc">2、每日晚上21:00,根据您的竞技场排行,系统将会通过邮件发放每日奖励!</div>

    <div class="ranklist" style="margin-top:30px;margin-bottom:9px;">
      <div class="rankleft" style="color:#999;font-size:12px">排名</div>
      <div class="rankright" style="color:#999;font-size:12px">奖励</div>
    </div>
    <div class="ranklist" style="height:56px;" v-for="(item,key) in rewards" :key="key">
      <div class="rankleft">{{item.rank}}</div>
      <div class="rankright">
        <div style="position:relative;width:32px; height:32px; border:1px solid #ccc; text-align:center;">
          <img src="../../img/weekly_salary_crystal@2x.png" width="100%" height="100%">
          <span style="width:100%; height:12px; line-height:12px; position:absolute; bottom:0px; left:0px; right:0px; color:#fff;font-size:10px;text-align:center;">
            {{item.reward_num1}}
          </span>
        </div>
        <div style="position:relative;width:32px; height:32px; border:1px solid #ccc; text-align:center;">
          <img src="../../img/weekly_salary_jjc@2x.png" width="100%" height="100%">
          <span style="width:100%; height:12px; line-height:12px; position:absolute; bottom:0px; left:0px; right:0px; color:#fff;font-size:10px;text-align:center;">
            {{item.reward_num2}}
          </span>
        </div>
        <div style="position:relative;width:32px; height:32px; border:1px solid #ccc; text-align:center;">
          <img src="../../img/weekly_salary_dimensity@2x.png" width="100%" height="100%">
          <span style="width:100%; height:12px; line-height:12px; position:absolute; bottom:0px; left:0px; right:0px; color:#fff;font-size:10px;text-align:center;">
            {{item.reward_num3}}
          </span>
        </div>
      </div>
    </div>

    <div class="section">
        <div class="line"></div>
        <div class="tip">战斗规则</div>
    </div>
    <div class="desc">1、需要分别设置进攻队伍和防守队伍,2个队伍相互独立!</div>
    <div class="desc">2、在竞技场中无法进行操作,只能自动战斗</div>
    <div class="desc">3、只有进攻方玩家获胜且进攻方的当前排名低于防守方玩家,双方排名才会互换。</div>
    <div class="desc">4、五分钟内战斗结束,按进攻失败处理!</div>
    <div class="desc">5、每日凌晨2点,刷新五次免费的进攻机会,每次战斗结算都需要等待CD后,才能继续挑战</div>
  </div>
</template>

<script>
export default {
  data () {
    return {
      rewards: [
        {'rank': '第1名', 'reward_num1': '50k', 'reward_num2': '3000', 'reward_num3': '200'},
        {'rank': '第2、3名', 'reward_num1': '40k', 'reward_num2': '2500', 'reward_num3': '150'},
        {'rank': '第4~10名', 'reward_num1': '30k', 'reward_num2': '2000', 'reward_num3': '50'},
        {'rank': '第11~100名', 'reward_num1': '28k', 'reward_num2': '1500', 'reward_num3': '30'}
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
      this.rewards = window.CosBox.getJjcRewards()
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

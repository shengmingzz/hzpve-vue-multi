<template>
  <div id="app">
    <img src="../../img/thumb_mxzl@2x.png" style="width:100%" @onclick.native="tapArticle(1,2)">
    <div class="chapter" v-for="(item, key) in datas" :key="key">
      <div class="charptertitle">{{item.name}}</div>
      <img class="charpterline" src="../../img/break_line@2x.png">
      <div class="mission" v-for="(mission, subkey) in item.mission" :key="subkey" >
        <div @onclick.native="tapArticle(key,subkey)" class="missiontitle">{{mission.name}}</div>

        <div class="missiondetail" v-show="isShowDetail(key, subkey)">
          <div class="missionsitution">
            <div class="missioncondition">
              <div class="section">
                  <div class="line"></div>
                  <div class="tip">通关条件</div>
              </div>
              <div class="star" style="margin-top:12px;">
                <img src="../../img/hero_star@2x.png" style="width:16px;height:16px;margin-right:8px">
                击杀埃及艳后
              </div>
              <div class="star" style="margin-top:12px;">
                <img src="../../img/hero_star@2x.png" style="width:16px;height:16px;margin-right:8px">
                顺利通关
              </div>
              <div class="star" style="margin-top:12px;">
                <img src="../../img/hero_star@2x.png" style="width:16px;height:16px;margin-right:8px">
                击杀任意怪物
              </div>
            </div>
            <div class="missondiff">
              <div class="section">
                  <div class="line"></div>
                  <div class="tip">关卡难度</div>
              </div>
              <div>
                <img @click="clickDifficultNormal()" src="../../img/level_normal_on@2x.png" style="width:40px;height:40px;">
                <img @click="clickDifficultHard()" src="../../img/level_difficulty_on@2x.png" style="width:40px;height:40px;">
              </div>
            </div>
          </div>
          <div class="section">
              <div class="line"></div>
              <div class="tip">推荐战斗力</div>
          </div>
          <div class="desc">20000</div>
          <div class="section">
              <div class="line"></div>
              <div class="tip">通关奖励</div>
          </div>
          <div class="reward">
            <img class="rewardimg" src="../../img/award_honor@2x.png">
            <div class="item">
              <div class="itemtitle">荣誉点</div>
              <div class="itemdesc">参与混沌遗迹即可获得,可以用于荣誉商店消费。</div>
            </div>
          </div>
        </div>
        <img class="charpterline" src="../../img/break_line@2x.png">
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data () {
    return {
      datas: [],
      index: -1,
      subindex: -1,
      difficult: 0
    }
  },
  components: {},
  computed: {},
  mounted () {
    this.loadData()
  },
  methods: {
    loadData () {
      this.datas = window.CosBox.getChapter()
    },
    tapArticle (key, subkey) {
      console.log('1234')
      // this.index = key
      // this.subkey = subkey
    },
    isShowDetail (key, subkey) {
      if (this.index === key && this.subindex === subkey) {
        return true
      }
      return false
    },
    clickDifficultNormal () {
      this.difficult = 0
    },
    clickDifficultHard () {
      this.difficult = 1
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

.chapter {
  display: flex;
  flex-direction: column;
  align-items: center;
}
.charptertitle {
  font-size: 0.7rem;
  color: #e77e11;
  text-align: center;
  margin-top: 1.5rem;
}
.charpterline {
  margin-top: 0.8rem;
  margin-bottom: 0.6rem;
  margin-left: 1.2rem;
  margin-right: 1.2rem;
  height: 0.4rem;
}
.mission {
  display: flex;
  flex-direction: column;
  align-items: center;
}
.missiontitle {
  font-size: 0.7rem;
  color: #333;
}
.missiondetail {
  margin-top: 1.75rem;
  margin-left: 1.2rem;
  margin-right: 1.2rem;
  margin-bottom: 1.2rem;
}
.missionsitution {
  display: flex;
  flex-direction: row;
}
.missioncondition {
  display: flex;
  flex-direction: column;
  flex: 1;
}
.missondiff {
  display: flex;
  flex-direction: column;
  flex: 1;
}
.star {
  display: flex;
  flex-direction: row;
  font-size: 14px;
  color: #333;
  align-items: center;
}
</style>

<template>
  <div class="form" style="margin-bottom:50px;">

    <el-form ref="form" :inline="true" label-width="100px">
      <!--      <el-form-item label="目标星级">-->
      <!--        <el-input v-model="star" style="width: 100px;" type="number"-->
      <!--                  oninput="this.value = this.value.replace(/[^0-9]/g, '');">-->
      <!--        </el-input>-->
      <!--      </el-form-item>-->


    </el-form>

    <el-form ref="form" label-width="100px">
      <el-form-item label="宝石初始星">
        <el-input-number v-model="initialstar" style="width: 100px;" :min="0" :max="14" :step="1" step-strictly
                         @change="setInitial()"/>
      </el-form-item>
      <el-form-item label="宝石目标星">
        <el-input-number v-model="finalstar" style="width: 100px;" :min="finalstarmin" :max="finalstarmax" :step="1"
                         step-strictly @change="setFinal()"/>
        <span readonly="true" v-html="final_star_explain"></span>
      </el-form-item>
      <el-form-item label="成功率加成">
        <el-input v-model="bonus" oninput="this.value = this.value.replace(/[^0-9]/g, '');" style="width: 100px;">
          <template #append>%</template>
        </el-input>
      </el-form-item>
      <el-form-item label="四叶草选择">
        <el-select v-model="clover1" class="m-2" placeholder="1升2">
          <el-option-group
              :label='"1升2"'
          />
          <el-option
              v-for="item in options"
              :key="item.value"
              :label="item.label"
              :value="item.value"
          />
        </el-select>
        <el-select v-model="clover2" class="m-2" placeholder="2升3">
          <el-option-group
              :label='"2升3"'
          />
          <el-option
              v-for="item in options"
              :key="item.value"
              :label="item.label"
              :value="item.value"
          />
        </el-select>
        <el-select v-model="clover3" class="m-2" placeholder="3升4">
          <el-option-group
              :label='"3升4"'
          />
          <el-option
              v-for="item in options"
              :key="item.value"
              :label="item.label"
              :value="item.value"
          />
        </el-select>
        <el-select v-model="clover4" class="m-2" placeholder="4升5">
          <el-option-group
              :label='"4升5"'
          />
          <el-option
              v-for="item in options"
              :key="item.value"
              :label="item.label"
              :value="item.value"
          />
        </el-select>
        <el-select v-model="clover5" class="m-2" placeholder="5升6">
          <el-option-group
              :label='"5升6"'
          />
          <el-option
              v-for="item in options"
              :key="item.value"
              :label="item.label"
              :value="item.value"
          />
        </el-select>
        <el-select v-model="clover6" class="m-2" placeholder="6升7">
          <el-option-group
              :label='"6升7"'
          />
          <el-option
              v-for="item in options"
              :key="item.value"
              :label="item.label"
              :value="item.value"
          />
        </el-select>
        <el-select v-model="clover7" class="m-2" placeholder="7升8">
          <el-option-group
              :label='"7升8"'
          />
          <el-option
              v-for="item in options"
              :key="item.value"
              :label="item.label"
              :value="item.value"
          />
        </el-select>
        <el-select v-model="clover8" class="m-2" placeholder="8升9">
          <el-option-group
              :label='"8升9"'
          />
          <el-option
              v-for="item in options"
              :key="item.value"
              :label="item.label"
              :value="item.value"
          />
        </el-select>
        <el-select v-model="clover9" class="m-2" placeholder="9升10">
          <el-option-group
              :label='"9升10"'
          />
          <el-option
              v-for="item in options"
              :key="item.value"
              :label="item.label"
              :value="item.value"
          />
        </el-select>
        <el-select v-model="clover10" class="m-2" placeholder="10升11">
          <el-option-group
              :label='"10升11"'
          />
          <el-option
              v-for="item in options"
              :key="item.value"
              :label="item.label"
              :value="item.value"
          />
        </el-select>
        <el-select v-model="clover11" class="m-2" placeholder="11升12">
          <el-option-group
              :label='"11升12"'
          />
          <el-option
              v-for="item in options"
              :key="item.value"
              :label="item.label"
              :value="item.value"
          />
        </el-select>
        <el-select v-model="clover12" class="m-2" placeholder="12升13">
          <el-option-group
              :label='"12升13"'
          />
          <el-option
              v-for="item in options"
              :key="item.value"
              :label="item.label"
              :value="item.value"
          />
        </el-select>
        <el-select v-model="clover13" class="m-2" placeholder="13升14">
          <el-option-group
              :label='"13升14"'
          />
          <el-option
              v-for="item in options"
              :key="item.value"
              :label="item.label"
              :value="item.value"
          />
        </el-select>
        <el-select v-model="clover14" class="m-2" placeholder="14升15">
          <el-option-group
              :label='"14升15"'
          />
          <el-option
              v-for="item in options"
              :key="item.value"
              :label="item.label"
              :value="item.value"
          />
        </el-select>
      </el-form-item>
      <el-form-item label="保险金选择">
        <el-checkbox v-model="insurance6" label="上7" size="large"/>
        <el-checkbox v-model="insurance7" label="上8" size="large"/>
        <el-checkbox v-model="insurance8" label="上9" size="large"/>
        <el-checkbox v-model="insurance9" label="上10" size="large"/>
        <el-checkbox v-model="insurance10" label="上11" size="large"/>
        <el-checkbox v-model="insurance11" label="上12" size="large"/>
        <el-checkbox v-model="insurance12" label="上13" size="large"/>
        <el-checkbox v-model="insurance13" label="上14" size="large"/>
        <el-checkbox v-model="insurance14" label="上15" size="large"/>
      </el-form-item>


      <el-form-item>
        <el-button :icon="Star" type="primary" @click="Recommend()">一键勾选
        </el-button>

      </el-form-item>
      <!--      <el-form-item>-->
      <!--        <el-button :icon="Setting" type="primary" @click="test()">推荐四叶草(这个功能仅用于测试，正式版不会出现)-->
      <!--        </el-button>-->

      <!--      </el-form-item>-->
      <el-form-item>
        <el-button :icon="MagicStick" type="primary" @click="clearClover()">清空四叶草
        </el-button>
      </el-form-item>
      <el-form-item>

        <el-button :icon="EditPen" type="primary" @click="Calculate()">计算
        </el-button>
      </el-form-item>

      <br>
      <el-divider><p id="result" style="font-size: 18px;font-weight: bold">计算结果</p></el-divider>
      <br>

      <el-form-item label="水晶消耗量">
        <img style="visibility: hidden" src="src/assets/imgs/transparent.png">
        <img style="visibility: hidden;position: absolute" id="normal" src="src/assets/imgs/0x12700010.png">
        <span readonly="true" v-html="normalcost"></span>
        <img style="visibility: hidden;position: absolute" id="abnormal" src="src/assets/imgs/0x12700120.png">
        <span readonly="true" v-html="abnormalcost"></span>
      </el-form-item>

      <el-form-item label="四叶草消耗">
        <span readonly="true" id="noconsume"
              style="visibility: hidden;position: absolute">不消耗任何6草以上的四叶草</span>
        <img style="visibility: hidden" id="clover6" src="src/assets/imgs/clover6.png">
        <span readonly="true" v-html="clover6cost"></span>
        <img style="visibility: hidden" id="S" src="src/assets/imgs/S.png">
        <span readonly="true" v-html="scost"></span>
        <img style="visibility: hidden" id="SS" src="src/assets/imgs/SS.png">
        <span readonly="true" v-html="sscost"></span>
        <img style="visibility: hidden" id="SSS" src="src/assets/imgs/SSS.png">
        <span readonly="true" v-html="ssscost"></span>
        <img style="visibility: hidden" id="SSR" src="src/assets/imgs/SSR.png">
        <span readonly="true" v-html="ssrcost"></span>
      </el-form-item>

      <el-form-item label="点券消耗量">
        <span readonly="true" v-html="pointcost"></span>
        <img id="D" style="visibility: hidden" src="src/assets/imgs/D.png">
      </el-form-item>

      <el-form-item label="保险节省量">
        <img style="visibility: hidden" src="src/assets/imgs/transparent.png">
        <img style="visibility: hidden;position: absolute" id="normal1" src="src/assets/imgs/0x12700010.png">
        <img style="visibility: hidden;position: absolute" id="abnormal1" src="src/assets/imgs/0x12700120.png">
        <span readonly="true" v-html="insurancesave"></span>
      </el-form-item>

      <el-form-item label="节省水晶价">
        <span readonly="true" v-html="insurancesaved"></span>
      </el-form-item>


    </el-form>

  </div>
</template>

<script setup>

import {ref} from "vue";
import {EditPen, Star, MagicStick} from "@element-plus/icons-vue";

//const star = ref("");  //星级变量
//const num = ref("");   //卡牌数变量
const bonus = ref("");  //成功率加成变量
const initialstar = ref("0");  //宝石初始星级
const finalstar = ref("0");
const finalstarmin = ref("1");
const finalstarmax = ref("15");//宝石目标星级
const final_star_explain = ref("");
const clover1 = ref(""); //定义四叶草变量
const clover2 = ref("");
const clover3 = ref("");
const clover4 = ref("");
const clover5 = ref("");
const clover6 = ref("");
const clover7 = ref("");
const clover8 = ref("");
const clover9 = ref("");
const clover10 = ref("");
const clover11 = ref("");
const clover12 = ref("");
const clover13 = ref("");
const clover14 = ref("");
const insurance6 = ref(false)
const insurance7 = ref(false)
const insurance8 = ref(false)
const insurance9 = ref(false)
const insurance10 = ref(false)
const insurance11 = ref(false)
const insurance12 = ref(false)
const insurance13 = ref(false)
const insurance14 = ref(false)
const normalcost = ref("")
const abnormalcost = ref("")
const pointcost = ref("")
const clover6cost = ref("")
const scost = ref("")
const sscost = ref("")
const ssscost = ref("")
const ssrcost = ref("")
const insurancesave = ref("")
const insurancesaved = ref("")


const options = [
  {
    value: 1.0,
    label: '不加草',
  },
  {
    value: 1.2,
    label: '1级四叶草',
  },
  {
    value: 1.4,
    label: '2级四叶草',
  },
  {
    value: 1.7,
    label: '3级四叶草',
  },
  {
    value: 2.0,
    label: '4级四叶草',
  },
  {
    value: 2.4,
    label: '5级四叶草',
  },
  {
    value: 2.7,
    label: '6级四叶草',
  },
  {
    value: 3.0,
    label: '超能四叶草',
  },
  {
    value: 3.2,
    label: 'SS四叶草',
  },
  {
    value: 3.6,
    label: 'SSS四叶草',
  },
  {
    value: 4.0,
    label: 'SSR四叶草',
  },

]
//定义概率表，宝石主卡为0-15rate[0]-rate[14]
const rate = [1, 0.88, 0.75, 0.63, 0.5, 0.38, 0.26, 0.19, 0.13, 0.10, 0.09, 0.08, 0.07, 0.06, 0.05]

//定义宝石消耗表
const crystalcost = [5, 10, 15, 25, 35, 55, 75, 100, 130, 160, 200, 245, 300, 355, 420]
const insurancecost = [0, 0, 0, 0, 0, 0, 400, 500, 600, 2500, 3000, 3500, 4000, 4500, 5000]
const no_insurance = [false, false, false, false, false, false, false, false, false, false, false, false, false, false, false]

function setInitial() {
  finalstarmin.value = initialstar.value + 1;
  finalstar.value = (initialstar.value >= 10) ? String(15) : String(10);
  finalstarmax.value = (initialstar.value >= 10) ? String(15) : String(10);
  if (initialstar.value < 10 && finalstar.value == 10) {
    final_star_explain.value = "&emsp;初始星低于10时目标星不能超过10";
  }
  if (initialstar.value >= 10) {
    final_star_explain.value = "";
  }
}

function setFinal() {
  if (initialstar.value >= finalstar.value) {
    initialstar.value = String(finalstar.value - 1);
  }
  if (finalstar.value > 10 && initialstar.value < 10) {
    initialstar.value = "10";
  }
}

//打开消息提示框
import {ElMessageBox} from 'element-plus'
import {ElNotification} from 'element-plus'

window.onload = function open() {
  ElMessageBox.alert('美食计算器交流群301119931，使用前请注意下方说明', '提醒', {
    confirmButtonText: '确定',
  })
}
//问卷调查
const success = (title, text) => {
  ElNotification({
    title: title,
    dangerouslyUseHTMLString: true,
    message: text,
    type: 'success',
    duration: 3000,
  })
}
const exeception = (title, text) => {
  ElNotification({
    title: title,
    dangerouslyUseHTMLString: true,
    message: text,
    type: 'error',
    duration: 3000,
  })
}
const info = (title, text) => {
  ElNotification({
    title: title,
    dangerouslyUseHTMLString: true,
    message: text,
    type: 'info',
    duration: 1500,
  })
}

const rateValid = (rate) => {
  if (rate >= 1) {
    return 1;
  } else {
    return rate;
  }
}

//填入推荐参数函数
function Recommend() {
  if (!(insurance6.value && insurance7 && insurance8 && insurance9 && insurance10 && insurance11 && insurance12 && insurance13 && insurance14)) {
    insurance6.value = true;
    insurance7.value = true;
    insurance8.value = true;
    insurance9.value = true;
    insurance10.value = true;
    insurance11.value = true;
    insurance12.value = true;
    insurance13.value = true;
    insurance14.value = true;
  } else {
    insurance6.value = false;
    insurance7.value = false;
    insurance8.value = false;
    insurance9.value = false;
    insurance10.value = false;
    insurance11.value = false;
    insurance12.value = false;
    insurance13.value = false;
    insurance14.value = false;
  }
  info("勾选完成", "已为你勾选所有保险");
}

//测试函数


//清空四叶草情况
function clearClover() {
  clover1.value = "";
  clover2.value = "";
  clover3.value = "";
  clover4.value = "";
  clover5.value = "";
  clover6.value = "";
  clover7.value = "";
  clover8.value = "";
  clover9.value = "";
  clover10.value = "";
  clover11.value = "";
  clover12.value = "";
  clover13.value = "";
  clover14.value = "";
  info("清除完成", "已清除所有四叶草")
}

//入口函数
function Calculate() {
  //判断条件
  if (initialstar.value >= 15) {
    exeception("计算出错", "宝石初始星级不合法");
    initialstar.value = "";
    return;
  }
  if (initialstar.value == "") {
    initialstar.value = "0";
  }
  //是否使用保险金的Boolean数组
  var insurance = [false, false, false, false, false, false, insurance6.value, insurance7.value, insurance8.value, insurance9.value, insurance10.value, insurance11.value, insurance12.value, insurance13.value, insurance14.value];
  //点券计算部分
  var totalpoint = pointCalculate(initialstar.value, finalstar.value - 1, insurance);
  //水晶计算部分
  var abnormal = abnormalCrystalCalculate(initialstar.value, finalstar.value - 1, insurance) - abnormalCrystalCalculate(initialstar.value, initialstar.value - 1, insurance);
  var normal = normalCrystalCalculate(initialstar.value, finalstar.value - 1, insurance) - normalCrystalCalculate(initialstar.value, initialstar.value - 1, insurance);
  //四叶草计算部分
  var clover = cloverCalculate(initialstar.value, finalstar.value - 1, insurance);
  var clover_initial = cloverCalculate(initialstar.value, initialstar.value - 1, insurance);
  var clover6 = clover[0] - clover_initial[0];
  var clovers = clover[1] - clover_initial[1];
  var cloverss = clover[2] - clover_initial[2];
  var cloversss = clover[3] - clover_initial[3];
  var cloverssr = clover[4] - clover_initial[4];
  //保险节省量
  var abnormalcrystalsave;
  abnormalcrystalsave = abnormalCrystalCalculate(initialstar.value, finalstar.value - 1, no_insurance) * 1.0 - abnormalCrystalCalculate(initialstar.value, initialstar.value - 1, no_insurance) * 1.0 - abnormal * 1.0;

  var normalcrystalsave;
  normalcrystalsave = normalCrystalCalculate(initialstar.value, finalstar.value - 1, no_insurance) * 1.0 - normalCrystalCalculate(initialstar.value, initialstar.value - 1, no_insurance) * 1.0 - normal * 1.0;


  ShowResult(totalpoint, normal, abnormal, clover6, clovers, cloverss, cloversss, cloverssr, normalcrystalsave, abnormalcrystalsave);


}

function ShowResult(d, normal, abnormal, clover6, clovers, cloverss, cloversss, cloverssr, normalcrystalsave, abnormalcrystalsave) {
  if (initialstar.value >= 10) { //上15情况
    document.getElementById("abnormal").style.visibility = "visible";
    document.getElementById("abnormal1").style.visibility = "visible";
    abnormalcost.value = "x" + String(Math.round(abnormal));
    document.getElementById("normal").style.visibility = "hidden";
    document.getElementById("normal1").style.visibility = "hidden";
    normalcost.value = "";
    document.getElementById("result").innerHTML = "从<img id='initialstar'</img>上<img id='finalstar'</img>需要"
    document.getElementById("initialstar").src = '/src/assets/imgs/' + initialstar.value + '.png'
    document.getElementById("finalstar").src = '/src/assets/imgs/' + finalstar.value + '.png'
    insurancesave.value = "x" + String(Math.round(abnormalcrystalsave));
    insurancesaved.value = String(Math.floor(d / abnormalcrystalsave * 100) / 100) + "点券/个";
  } else { //上10情况
    document.getElementById("normal").style.visibility = "visible";
    document.getElementById("normal1").style.visibility = "visible";
    normalcost.value = "x" + String(Math.round(normal));
    document.getElementById("abnormal").style.visibility = "hidden";
    document.getElementById("abnormal1").style.visibility = "hidden";
    abnormalcost.value = "";
    document.getElementById("result").innerHTML = "从<img id='initialstar'</img>上<img id='finalstar'</img>需要"
    document.getElementById("initialstar").src = '/src/assets/imgs/' + initialstar.value + '.png'
    document.getElementById("finalstar").src = '/src/assets/imgs/' + finalstar.value + '.png'
    insurancesave.value = "x" + String(Math.round(normalcrystalsave));
    insurancesaved.value = String(Math.floor(d / normalcrystalsave * 100) / 100) + "点券/个";
  }
  if (clover6 || clovers || cloverss || cloversss || cloverssr) {
    document.getElementById("noconsume").style.visibility = "hidden";
    document.getElementById("clover6").style.visibility = "visible";
    document.getElementById("S").style.visibility = "visible";
    document.getElementById("SS").style.visibility = "visible";
    document.getElementById("SSS").style.visibility = "visible";
    document.getElementById("SSR").style.visibility = "visible";
    clover6cost.value = "<br>x" + String(Math.floor(clover6 * 100) / 100);
    scost.value = "<br>x" + String(Math.floor(clovers * 100) / 100);
    sscost.value = "<br>x" + String(Math.floor(cloverss * 100) / 100);
    ssscost.value = "<br>x" + String(Math.floor(cloversss * 100) / 100);
    ssrcost.value = "<br>x" + String(Math.floor(cloverssr * 100) / 100);
  } else {
    document.getElementById("noconsume").style.visibility = "visible";
    document.getElementById("clover6").style.visibility = "hidden";
    document.getElementById("S").style.visibility = "hidden";
    document.getElementById("SS").style.visibility = "hidden";
    document.getElementById("SSS").style.visibility = "hidden";
    document.getElementById("SSR").style.visibility = "hidden";
    clover6cost.value = "";
    scost.value = "";
    sscost.value = "";
    ssscost.value = "";
    ssrcost.value = "";
  }

  if (d) {
    pointcost.value = String(Math.round(d));
    document.getElementById("D").style.visibility = "visible";
  } else {
    pointcost.value = "0";
    document.getElementById("D").style.visibility = "visible";
  }
  success("计算成功", "当前版本v1.3<br>交流群301119931<br>欢迎参加我们的<a href=\"https://survey.xiayeqz.com:3999/s/QEFoBL\" style=\"text-decoration: none;color: #409EFF\" target=\"_blank\">问卷调查</a></strong>");
}

function pointCalculate(initialstar, mainstar, insurance) {
  var cost = 0;
  if (mainstar < 6) return 0;//上6截止
  if (mainstar >= 6 && mainstar < 15) {
    if (insurance[mainstar] == true) {
      cost += pointCalculate(initialstar, mainstar - 1, insurance);
      cost += insurancecost[mainstar] * 1 / rateCalculate(mainstar);
    }
    if (insurance[mainstar] == false) {
      cost += pointCalculate(initialstar, mainstar - 1, insurance);
      cost += (1 / rateCalculate(mainstar) - 1) * (pointCalculate(initialstar, mainstar - 1, insurance) - pointCalculate(initialstar, mainstar - 2, insurance));
    }
  }
  return cost;
}

function rateCalculate(mainstar) {
  //将用户输入的四叶草数值存储到数组中,这里自动排除不填的问题，当作不加草判断
  var clover = [1, (clover1.value > 0) ? clover1.value : 1, (clover2.value > 0) ? clover2.value : 1, (clover3.value > 0) ? clover3.value : 1, (clover4.value > 0) ? clover4.value : 1, (clover5.value > 0) ? clover5.value : 1, (clover6.value > 0) ? clover6.value : 1, (clover7.value > 0) ? clover7.value : 1, (clover8.value > 0) ? clover8.value : 1, (clover9.value > 0) ? clover9.value : 1, (clover10.value > 0) ? clover10.value : 1, (clover11.value > 0) ? clover11.value : 1, (clover12.value > 0) ? clover12.value : 1, (clover13.value > 0) ? clover13.value : 1, (clover14.value > 0) ? clover14.value : 1];
  return (rateValid((1.0 + 1.0 * bonus.value / 100) * rate[mainstar] * clover[mainstar]));
}


function normalCrystalCalculate(initialstar, mainstar, insurance) {
  var cost = 0;
  //if (mainstar < initialstar) return 0;//需要计算的星级小于预定的初始星，直接返回0
  if (mainstar < 0) return 0;//上0截止
  if (mainstar >= 6 && mainstar < 10) {
    if (insurance[mainstar] == true) {
      cost += normalCrystalCalculate(initialstar, mainstar - 1, insurance);
      cost += crystalcost[mainstar] * 1 / rateCalculate(mainstar);
    }
    if (insurance[mainstar] == false) {
      cost += crystalcost[mainstar] * 1 / rateCalculate(mainstar);
      cost += normalCrystalCalculate(initialstar, mainstar - 1, insurance);
      cost += (1 / rateCalculate(mainstar) - 1) * (normalCrystalCalculate(initialstar, mainstar - 1, insurance) - normalCrystalCalculate(initialstar, mainstar - 2, insurance));
    }
  }
  if (mainstar <= 5) {
    cost += 1 / rateCalculate(mainstar) * crystalcost[mainstar];
    cost += normalCrystalCalculate(initialstar, mainstar - 1, insurance);
  }
  return cost;
}

function abnormalCrystalCalculate(initialstar, mainstar, insurance) {

  var cost = 0;
  //if (mainstar < initialstar) return 0;//需要计算的星级小于预定的初始星，直接返回0
  if (mainstar < 10) return 0;//上10截止
  if (insurance[mainstar] == true) {
    cost += abnormalCrystalCalculate(initialstar, mainstar - 1, insurance);
    cost += crystalcost[mainstar] * 1 / rateCalculate(mainstar);
  }
  if (insurance[mainstar] == false) {
    cost += crystalcost[mainstar] * 1 / rateCalculate(mainstar);
    cost += abnormalCrystalCalculate(initialstar, mainstar - 1, insurance);
    cost += (1 / rateCalculate(mainstar) - 1) * (abnormalCrystalCalculate(initialstar, mainstar - 1, insurance) - abnormalCrystalCalculate(initialstar, mainstar - 2, insurance));
  }
  return cost;
}


//四叶草计算函数
function cloverCalculate(initialstar, mainstar, insurance) {
  var cost = [0, 0, 0, 0, 0];
  var i = 0;
  if (initialstar < 10 && mainstar < 0) return cost;//上0截止
  if (initialstar >= 10 && mainstar < 10) return cost;//上10截止
  //将用户输入的四叶草数值存储到数组中,这里自动排除不填的问题，当作不加草判断
  var clover = [1, (clover1.value > 0) ? clover1.value : 1, (clover2.value > 0) ? clover2.value : 1, (clover3.value > 0) ? clover3.value : 1, (clover4.value > 0) ? clover4.value : 1, (clover5.value > 0) ? clover5.value : 1, (clover6.value > 0) ? clover6.value : 1, (clover7.value > 0) ? clover7.value : 1, (clover8.value > 0) ? clover8.value : 1, (clover9.value > 0) ? clover9.value : 1, (clover10.value > 0) ? clover10.value : 1, (clover11.value > 0) ? clover11.value : 1, (clover12.value > 0) ? clover12.value : 1, (clover13.value > 0) ? clover13.value : 1, (clover14.value > 0) ? clover14.value : 1];
  //6草
  if (clover[mainstar] == 2.7) {
    if (mainstar >= 6) {
      if (insurance[mainstar] == true) {
        cost[0] += 1 / rateCalculate(mainstar);
        for (i = 0; i <= 4; i++)
          cost[i] += cloverCalculate(initialstar, mainstar - 1, insurance)[i];
      }
      if (insurance[mainstar] == false) {
        cost[0] += 1 / rateCalculate(mainstar);
        for (i = 0; i <= 4; i++) {
          //alert(i)
          cost[i] += cloverCalculate(initialstar, mainstar - 1, insurance)[i];
          cost[i] += (1 / rateCalculate(mainstar) - 1) * (cloverCalculate(initialstar, mainstar - 1, insurance)[i] - cloverCalculate(initialstar, mainstar - 2, insurance)[i]);
        }
      }
    }
    if (mainstar <= 5) {
      cost[0] += 1 / rateCalculate(mainstar);
      for (i = 0; i <= 4; i++)
        cost[i] += cloverCalculate(initialstar, mainstar - 1, insurance)[i];

    }
    return cost;
  }
  //S草
  if (clover[mainstar] == 3.0) {
    if (mainstar >= 6) {
      if (insurance[mainstar] == true) {
        cost[1] += 1 / rateCalculate(mainstar);
        for (i = 0; i <= 4; i++)
          cost[i] += cloverCalculate(initialstar, mainstar - 1, insurance)[i];
      }
      if (insurance[mainstar] == false) {
        cost[1] += 1 / rateCalculate(mainstar);
        for (i = 0; i <= 4; i++) {
          //alert(i)
          cost[i] += cloverCalculate(initialstar, mainstar - 1, insurance)[i];
          cost[i] += (1 / rateCalculate(mainstar) - 1) * (cloverCalculate(initialstar, mainstar - 1, insurance)[i] - cloverCalculate(initialstar, mainstar - 2, insurance)[i]);
        }
      }
    }
    if (mainstar <= 5) {
      cost[1] += 1 / rateCalculate(mainstar);
      for (i = 0; i <= 4; i++)
        cost[i] += cloverCalculate(initialstar, mainstar - 1, insurance)[i];

    }
    return cost;
  }
//SS草
  if (clover[mainstar] == 3.2) {
    if (mainstar >= 6) {
      if (insurance[mainstar] == true) {
        cost[2] += 1 / rateCalculate(mainstar);
        for (i = 0; i <= 4; i++)
          cost[i] += cloverCalculate(initialstar, mainstar - 1, insurance)[i];
      }
      if (insurance[mainstar] == false) {
        cost[2] += 1 / rateCalculate(mainstar);
        for (i = 0; i <= 4; i++) {
          //alert(i)
          cost[i] += cloverCalculate(initialstar, mainstar - 1, insurance)[i];
          cost[i] += (1 / rateCalculate(mainstar) - 1) * (cloverCalculate(initialstar, mainstar - 1, insurance)[i] - cloverCalculate(initialstar, mainstar - 2, insurance)[i]);
        }
      }
    }
    if (mainstar <= 5) {
      cost[2] += 1 / rateCalculate(mainstar);
      for (i = 0; i <= 4; i++)
        cost[i] += cloverCalculate(initialstar, mainstar - 1, insurance)[i];

    }
    return cost;
  }
//SSS草
  if (clover[mainstar] == 3.6) {
    if (mainstar >= 6) {
      if (insurance[mainstar] == true) {
        cost[3] += 1 / rateCalculate(mainstar);
        for (i = 0; i <= 4; i++)
          cost[i] += cloverCalculate(initialstar, mainstar - 1, insurance)[i];
      }
      if (insurance[mainstar] == false) {
        cost[3] += 1 / rateCalculate(mainstar);
        for (i = 0; i <= 4; i++) {
          //alert(i)
          cost[i] += cloverCalculate(initialstar, mainstar - 1, insurance)[i];
          cost[i] += (1 / rateCalculate(mainstar) - 1) * (cloverCalculate(initialstar, mainstar - 1, insurance)[i] - cloverCalculate(initialstar, mainstar - 2, insurance)[i]);
        }
      }
    }
    if (mainstar <= 5) {
      cost[3] += 1 / rateCalculate(mainstar);
      for (i = 0; i <= 4; i++)
        cost[i] += cloverCalculate(initialstar, mainstar - 1, insurance)[i];

    }
    return cost;
  }
//SSR草
  if (clover[mainstar] == 4.0) {
    if (mainstar >= 6) {
      if (insurance[mainstar] == true) {
        cost[4] += 1 / rateCalculate(mainstar);
        for (i = 0; i <= 4; i++)
          cost[i] += cloverCalculate(initialstar, mainstar - 1, insurance)[i];
      }
      if (insurance[mainstar] == false) {
        cost[4] += 1 / rateCalculate(mainstar);
        for (i = 0; i <= 4; i++) {
          //alert(i)
          cost[i] += cloverCalculate(initialstar, mainstar - 1, insurance)[i];
          cost[i] += (1 / rateCalculate(mainstar) - 1) * (cloverCalculate(initialstar, mainstar - 1, insurance)[i] - cloverCalculate(initialstar, mainstar - 2, insurance)[i]);
        }
      }
    }
    if (mainstar <= 5) {
      cost[4] += 1 / rateCalculate(mainstar);
      for (i = 0; i <= 4; i++)
        cost[i] += cloverCalculate(initialstar, mainstar - 1, insurance)[i];

    }
    return cost;
  }
  //不加草and其他草处理方式
  if (mainstar >= initialstar)
    return cloverCalculate(initialstar, mainstar - 1, insurance);
  else
    return cost;
}
</script>

<style scoped>
.form {
  font-family: 'Helvetica Neue', Helvetica, 'PingFang SC', 'Hiragino Sans GB',
  'Microsoft YaHei', '微软雅黑', Arial, sans-serif;
}
</style>
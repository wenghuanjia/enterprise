<template>
  <div class="index" @click="show_out">
    <!-- 服务商 -->
    <div class="index_left sidebar-small">
      <div class="serve">
        <h4>服务商</h4>
      </div>
      <el-collapse v-model="activeNames" @change="handleChange" class="title">
        <el-collapse-item title="服务公司" name="1">
          <div class="company">
            <div class="company_item">
              <p>广州文明底蕴信息科技有限公司</p>
              <p>
                <span>孙先生</span>
                <span>13002093311</span>
              </p>
            </div>
          </div>
        </el-collapse-item>
        <el-collapse-item title="研发公司" name="2">
          <div class="company">
            <div class="company_item">
              <p>广州文明底蕴信息科技有限公司</p>
              <p>
                <span>孙先生</span>
                <span>13002093311</span>
              </p>
            </div>
          </div>
        </el-collapse-item>
        <el-collapse-item title="知识产权管理公司" name="3">
          <div class="company">
            <div class="company_item">
              <p>广州文明底蕴信息科技有限公司</p>
              <p>
                <span>孙先生</span>
                <span>13002093311</span>
              </p>
            </div>
            <div class="company_item">
              <p>广州文明底蕴信息科技有限公司</p>
              <p>
                <span>孙先生</span>
                <span>13002093311</span>
              </p>
            </div>
          </div>
        </el-collapse-item>
        <el-collapse-item title="申报公司" name="4">
          <div class="company">
            <div class="company_item">
              <p>广州文明底蕴信息科技有限公司</p>
              <p>
                <span>孙先生</span>
                <span>13002093311</span>
              </p>
            </div>
            <div class="company_item">
              <p>广州文明底蕴信息科技有限公司</p>
              <p>
                <span>孙先生</span>
                <span>13002093311</span>
              </p>
            </div>
            <div class="company_item">
              <p>广州文明底蕴信息科技有限公司</p>
              <p>
                <span>孙先生</span>
                <span>13002093311</span>
              </p>
            </div>
          </div>
        </el-collapse-item>
      </el-collapse>
      <!-- 用户 -->
      <div class="user" @click.stop="showOut">
        <div class="user_logo">
          <img src="../images/user.png" alt>
          <div class="user_name" v-if="userInfo">{{ userInfo.user_login }}</div>
        </div>
        <div class="login_out" v-if="show">
          <div class="menu" @click="goLogin">退出登陆</div>
        </div>
      </div>
    </div>
    <!-- 填写表格 -->
    <div class="index_right">
      <!-- 步骤 -->
      <div class="steps">
        <!-- <div style="height: 300px;">
          <el-steps direction="vertical" :active="2">
            <el-step title="每月填写研发费用比"></el-step>
            <el-step title="研发人员"></el-step>
            <el-step title="研发项目"></el-step>
            <el-step title="知识产权管理模块"></el-step>
            <el-step title="高新材料收集管理"></el-step>
          </el-steps>
        </div>-->
        <div class="step">
          <div class="step_item">
            <div class="address">
              <img src="../images/adderss.png" alt>
              <span class="data">填写的材料</span>
            </div>
          </div>
          <div style="height: 300px;">
            <el-steps direction="vertical" :active="current">
              <el-step
                v-for="(step,i) in steps"
                :key="i"
                :class="(i+1) == current?'currentStyle':''"
                :title="step.title"
                @click.native="handleChoose(i)"
              >
              </el-step>
            </el-steps>
          </div>
        </div>
      </div>
      <div class="means">
        <!-- 视图显示 -->
        <router-view></router-view>
      </div>
    </div>
  </div>
</template>
<script>
import { mapState, mapMutations } from "vuex";
import { addProject } from "service/getData"
export default {
  data() {
    return {
      activeNames: ["0"],
      tabPosition: "left",
      show: false,
      showarr: [],
      current: 1,
      steps: [
        { id: 1, title: "每月填写研发费用表" },
        { id: 2, title: "研发人员" },
        { id: 3, title: "研发项目" },
        { id: 4, title: "知识产权管理模块" },
        { id: 5, title: "高新材料收集管理" }
      ]
    };
  },
  methods: {
    handleChange(val) {
      console.log(val);
    },
    ...mapMutations(["OUT_LOGIN", "INIT_USERINFO", "SET_STATE_FLAG"]),
    // 退出登陆
    goLogin() {
      this.OUT_LOGIN();
      this.$router.push({ path: "/login" });
    },
    showOut() {
      this.show = !this.show;
    },
    // 点击屏幕隐藏退出按钮
    show_out() {
      if (this.show) {
        this.show = false;
      }
    },
    handleChoose(i) {
      i = i + 1;
      this.current = i;
      // this.$router.push({})
    }
  },
  computed: {
    ...mapState(["userInfo"])
  },
  async created() {
    this.INIT_USERINFO();
  }
};
</script>

<style lang="less">
.title .el-collapse-item div .el-collapse-item__header {
  padding-left: 31px;
}
.title .el-collapse-item .el-collapse-item__wrap .el-collapse-item__content {
  padding-bottom: 0;
  // padding-left: 31px;
}
.title .el-collapse-item .el-collapse-item__wrap {
  background: #f6f6f6;
}
.title .is-active {
  background-color: #e3edff;
  // opacity: 0.3;
  color: #297bfe;
}
.currentStyle .is-finish .is-text {
  border-color: #409eff;
}
.currentStyle .is-finish .el-step__icon-inner {
  color: #409eff;
}
.currentStyle .el-step__title.is-finish {
  color: #409eff;
}
.steps .is-wait,
.steps .is-process,
.steps .is-text {
  color: #c0c4cc;
  // color: #333;
  border-color: #c0c4cc;
  font-weight: 400;
}
.steps .el-step__title {
  color: #333;
  font-size: 14px;
}
.steps .el-step {
  cursor: pointer;
}

// 设置竖线的颜色
.steps .el-step__line-inner {
  height: 0px !important;
}
</style>

<style scoped lang="less">
@import "../style/mixin.less";
.index {
  display: flex;
  // height: 100%;
}
.sidebar-small {
  position: relative;
  position: fixed;
  width: 318px;
  // width: 230px;
  background: #ffffff;
  height: 100%;
  border-right: 1px solid #f6f6f6;
  .serve {
    color: #297bfe;
    h4 {
      padding: 6px 0 0 31px;
    }
  }
}
.company {
  // padding-left: 31px;
  .company_item {
    padding: 10px 0;
    padding-left: 31px;
    border-bottom: 1px solid #ebeef5;
    &:last-child {
      border: none;
    }
  }
  p {
    margin: 0;
    span {
      padding-right: 26px;
    }
  }
}
.user {
  width: 100%;
  position: absolute;
  bottom: 40px;
  cursor: pointer;
  .user_logo {
    display: flex;
    // flex-direction: column;
    justify-content: center;
    align-items: center;
    img {
      display: inline-block;
      width: 50px;
      height: 50px;
    }
    .user_name {
      padding-left: 8px;
    }
  }
  .login_out {
    transform-origin: center top 0px;
    z-index: 2007;
    position: absolute;
    top: 45px;
    // right: 50px;
    right: 70px;
    background-color: #fff;
    border: 1px solid #ebeef5;
    border-radius: 4px;
    box-shadow: 0 2px 12px 0 rgba(0, 0, 0, 0.1);
    text-align: center;
    &:hover {
      background-color: #eff3fc;
      color: #297bfe;
    }
    .menu {
      height: 40px;
      padding: 0 30px;
      line-height: 40px;
      border-bottom: 1px solid #dde2e3;
      &:after {
        content: "";
        position: absolute;
        top: -10px;
        left: 20%;
        width: 0;
        height: 0;
        border-left: 10px solid transparent;
        border-right: 10px solid transparent;
        border-bottom: 10px solid #fff;
      }
      &:before {
        content: "";
        position: absolute;
        top: -11px;
        left: 19%;
        width: 0;
        height: 0;
        border-left: 11px solid transparent;
        border-right: 11px solid transparent;
        border-bottom: 11px solid #ebeef5;
      }
    }
  }
}
.index_right {
  width: 100%;
  display: flex;
  box-shadow: #297bfc 0px 0px 10px;
  // padding-bottom: 20px;
  // margin-left: 20px;
  margin-left: 338px;
  margin-top: 1px;
  // margin-right: 20px;
  .steps {
    // height: 100%;
    // height: auto;
    width: 220px;
    padding: 30px;
    .step {
      .step_item {
        .address {
          padding-left: 4px;
          position: relative;
          &:after {
            position: relative;
            content: "";
            top: -1px;
            left: 7px;
            width: 2px;
            display: block;
            height: 54px;
            background: #c0c4cc;
          }
          img {
            width: 17px;
            height: 22px;
          }
          .data {
            margin-left: 8px;
          }
        }
      }
    }
  }
  .means {
    width: 100%;
    // height: 100%;
    padding-bottom: 20px;
  }
}
.currentStyle {}

</style>

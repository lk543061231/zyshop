<template>
    <div>
        <div class="wapnone fk_service">
      <ul>
        <li class="fk_service_box fk_service_ax2" v-if="username" @click="$router.push('/order')">
          <div class="fk_service_ax_cont2">
            <span class="fk_service_triangle2"></span>
            查看订单物流请点击
            <!-- <img src="../assets/iconP.png" alt="" /> -->
          </div>
        </li>
        <li class="fk_service_box fk_service_consult">
          <div class="fk_service_consult_cont">
            <span class="fk_service_triangle"></span>
            <div class="fk_service_consult_cont_top">
              <span class="fk_service_hint"></span>
              <span
                class="fk_service_button"
                onclick="window.open('https://wpa.qq.com/msgrd?v=3&uin=20838641&site=qq&menu=yes')"
                >QQ联系</span
              >
              <span
                class="fk_service_button"
                onclick="window.open('https://mail.qq.com/cgi-bin/qm_share?t=qm_mailme&email=771692826@qq.com')"
                >在线邮件</span
              >
            </div>
          </div>
        </li>

        <!-- 不需要图标的注释或删除即可 -->
        <!-- 联系我们 -->
        <li class="fk_service_box fk_service_ax">
          <div class="fk_service_ax_cont">
            <span class="fk_service_triangle"></span>
            联系我们:18614983835
            <!-- <img src="../assets/iconP.png" alt="" /> -->
          </div>
        </li>

        <li class="fk_service_box fk_service_ws">
          <div class="fk_service_ws_cont">
            <span class="fk_service_triangle"></span>
            企业微信请扫下方二维码
            <img id="qywxJpg" src="../assets/微信联系/企业微信.jpg" alt="" />
          </div>
        </li>

        <li class="fk_service_box fk_service_sd">
          <div class="fk_service_sd_cont">
            <span class="fk_service_triangle"></span>
            联系客服请扫二维码
            <img id="qywxJpg" src="../assets/微信联系/私人微信.jpg" alt="" />
          </div>
        </li>
        <li class="fk_service_box fk_service_sd to-top" v-if="showTop" @click="scrollTop">
          <i class="el-icon-upload2"></i>
        </li>
      </ul>
    </div>
    </div>
</template>

<script>
export default {
   data(){
        return {
            showTop:false
        }
    },
    props:{
        username:{
            default:''
        },
    },
    mounted(){
        window.addEventListener('scroll', ()=>{
            let scrollTop = window.pageYOffset || document.documentElement.scrollTop || document.body.scrollTop
                if(scrollTop>500){
                this.showTop=true
            }else{
                this.showTop=false
            }
        })
    },
    computed:{},
    methods:{
        scrollTop(){
            window.scrollTo({ top: 0, behavior: 'smooth' })
        },
    },
}
</script>
<style lang="less" scoped>

.fk_service {
  max-height: 232px;
  position: fixed;
  right: 2px;
  top: 50.2%;
  /* 垂直位置 */
  font-family: "Lucida Sans", "Lucida Sans Regular", "Lucida Grande",
    "Lucida Sans Unicode", Geneva, Verdana, sans-serif;
  color: #243558;
  z-index: 10000;
}
.fk_service ul {
  margin: 0;
  padding: 0;
  position: absolute;
  right: 0;
}
.fk_service li {
  list-style-type: none;
}
.fk_service li > div {
  box-sizing: border-box;
  box-shadow: 0 0 9px 0 rgba(0, 0, 0, 0.1);
}
.fk_service_box {
  width: 40px;
  height: 40px;
  background: #fff;
  margin-bottom: 10px;
  border-radius: 4px;
  box-sizing: border-box;
  box-shadow: 0 0 9px 0 rgba(0, 0, 0, 0.1);
}
.fk_service_triangle {
  top: 12px;
  right: -11px;
  position: absolute;
  border-top: 7px solid transparent;
  border-bottom: 7px solid transparent;
  border-left: 11px solid #e1e6ec;
  z-index: 1010;
}
.fk_service_triangle:after {
  content: "\20";
  top: -6px;
  right: 1px;
  position: absolute;
  border-top: 6px solid transparent;
  border-bottom: 6px solid transparent;
  border-left: 10px solid #fff;
  z-index: 1000;
}
.fk_service_triangle:before {
  content: "\20";
  width: 80px;
  height: 45px;
  top: -20px;
  right: -52px;
  position: absolute;
  background: rgba(0, 0, 0, 0);
}
@keyframes fade-in {
  0% {
    opacity: 0.4;
    right: 82px;
  }
  100% {
    opacity: 1;
    right: 62px;
  }
}
.fk_service_consult {
  background: url("../assets/QQQQ.png") no-repeat #fff center center;
  background-size: 70% 70%;
  z-index: 1;
}
// .fk_service_consult:hover {
//   border: 0;
//   background: url(../assets/客服.png) no-repeat -410px -16px #4f7cfc;
//   background-size: 40%40%;
// }
.fk_service_consult:hover .fk_service_consult_cont {
  display: block;
  opacity: 1;

  transition: linear 0.2s;
  animation-name: fade-in;
  animation-duration: 0.3s;
  animation-iteration-count: 1;
  animation-delay: 0s;
}
.fk_service_consult_cont {
  width: 200px;
  min-height: 210px;
  max-height: 268px;
  border-radius: 3px;
  background: #fff;
  right: 62px;
  position: absolute;
  text-align: center;
  border: 1px solid #e1e6ec;
  display: none;
  opacity: 0;
}
.fk_service_consult_cont1 {
  width: 70px;
  height: 40px;
  line-height: 40px;
  background: #fff;
  border-radius: 5px;
  right: 62px;
  text-align: center;
  position: absolute;
  display: none;
  border: 1px solid #e1e6ec;
}
.fk_service_consult_cont1 .fk_service_triangle:before {
  width: 0 !important;
}
.fk_service_consult_cont > .fk_service_triangle:after {
  border-left: 10px solid #f6f8fb !important;
}
.fk_service_consult_cont span {
  float: left;
}
.fk_service_consult_cont_top {
  width: 100%;
  height: 100%;
  background: #f6f8fb;
  border-radius: 3px;
  border-bottom: 1px solid #eef2f8;
}
.fk_service_hint {
  width: 100%;
  height: 40px;
  line-height: 40px;
  font-size: 12px;
  color: #9aa8c2;
  text-align: center;
}
.fk_service_hint > .fk_service_icon {
  background: url(https://www.zmki.cn/wp-content/uploads/2019/20190827-5d652476ab305.png)
    no-repeat -460px -25px;
  width: 15px;
  height: 15px;
  margin: 13px 2px 0 18px;
}
.fk_service_button {
  width: 160px;
  height: 38px;
  line-height: 38px;
  background: #4f7cfc;
  border-radius: 18px;
  text-align: center;
  color: #fff;
  margin: 5px 0 10px 20px;
  cursor: pointer;
}
// .fk_service_button:hover {
//   background: #618aff;
// }
.fk_service_phone {
  width: 100%;
  height: 53px;
  line-height: 53px;
  font-size: 14px;
  text-align: center;
}
.fk_service_check_site {
  width: 100%;
  height: 48px;
  line-height: 48px;
  color: #3b6bf4;
  border-top: 1px solid #eaeef5;
  cursor: pointer;
}
.fk_service_check_site > .fk_service_icon {
  background: url(https://www.zmki.cn/wp-content/uploads/2019/20190827-5d652476ab305.png)
    no-repeat -461px -75px;
  width: 20px;
  height: 20px;
  margin: 15px 2px 0 45px;
}
.fk_service_feedback {
  background: url(https://www.zmki.cn/wp-content/uploads/2019/20190827-5d652476ab305.png)
    no-repeat -363px -64px #fff;
}
.fk_service_feedback:hover {
  border: 0;
  background: url(https://www.zmki.cn/wp-content/uploads/2019/20190827-5d652476ab305.png)
    no-repeat -407px -64px #4f7cfc;
  cursor: pointer;
}
.fk_service_feedback:hover .fk_service_feedback_cont {
  display: block;
  opacity: 1;
  transition: linear 0.2s;
  animation-name: fade-in;
  animation-duration: 0.3s;
  animation-iteration-count: 1;
  animation-delay: 0s;
}
.fk_service_feedback_cont {
  width: 264px;
  height: 40px;
  line-height: 40px;
  background: #fff;
  border-radius: 5px;
  right: 62px;
  text-align: center;
  position: absolute;
  display: none;
  border: 1px solid #e1e6ec;
}
.fk_service_qr {
  background: url(https://www.zmki.cn/wp-content/uploads/2019/20190827-5d652476ab305.png)
    no-repeat -365px -113px #fff;
}
.fk_service_qr:hover {
  border: 0;
  background: url(https://www.zmki.cn/wp-content/uploads/2019/20190827-5d652476ab305.png)
    no-repeat -409px -113px #4f7cfc;
}
.fk_service_qr:hover .fk_service_qr_cont {
  display: block;
  opacity: 1;
  transition: linear 0.2s;
  animation-name: fade-in;
  animation-duration: 0.3s;
  animation-iteration-count: 1;
  animation-delay: 0s;
}
.fk_service_qr_cont {
  width: 143px;
  height: 202px;
  border-radius: 3px;
  background: #fff;
  right: 62px;
  position: absolute;
  text-align: center;
  border: 1px solid #e1e6ec;
  background-color: #f6f8fb;
  display: none;
  opacity: 0;
}
.fk_service_qr_cont > .fk_service_triangle:after {
  border-left: 10px solid #f6f8fb !important;
}
.fk_service_qr_cont > .fk_service_qrimg {
  width: 100%;
  height: 164px;
  float: left;
}
.fk_service_qrimg_site {
  width: 119px;
  height: 119px;
  float: left;
  margin: 12px 12px 5px 12px;
  background: url(https://www.zmki.cn/wp-content/uploads/2019/20190827-5d652476ab305.png)
    no-repeat -41px -26px;
}
.fk_service_qrimg_hd {
  width: 119px;
  height: 119px;
  float: left;
  margin: 12px 12px 5px 12px;
  background: url(https://www.zmki.cn/wp-content/uploads/2019/20190827-5d652476ab305.png)
    no-repeat -198px -26px;
}
.fk_service_qrimg_wxast {
  width: 119px;
  height: 119px;
  float: left;
  margin: 12px 12px 5px 12px;
  //报错
  // background: url(../image/fk_service.png?v=201905151200) no-repeat -198px -328px;
}
.fk_service_qrimg_flyer {
  width: 119px;
  height: 119px;
  float: left;
  margin: 12px 12px 5px 12px;
  background: url(https://www.zmki.cn/wp-content/uploads/2019/20190827-5d652476ab305.png)
    no-repeat -41px -177px;
}
.fk_service_qrimg_wxapp {
  width: 119px;
  height: 119px;
  float: left;
  margin: 12px 12px 5px 12px;
  background: url(https://www.zmki.cn/wp-content/uploads/2019/20190827-5d652476ab305.png)
    no-repeat -198px -177px;
}
.fk_service_qrimg_fkmall {
  width: 119px;
  height: 119px;
  float: left;
  margin: 12px 12px 5px 12px;
  background: url(https://www.zmki.cn/wp-content/uploads/2019/20190827-5d652476ab305.png)
    no-repeat -41px -326px;
}
.fk_service_qr_cont > .fk_service_qrtext {
  width: 100%;
  height: 35px;
  font-size: 12px;
  color: #7b89a6;
  background-color: #fff;
  float: left;
  bottom: 0;
  display: table;
}
.fk_service_qr_cont > .fk_service_qrtext > span {
  display: table-cell;
  vertical-align: middle;
}
.fk_service_upward {
  display: none;
  background: url(https://www.zmki.cn/wp-content/uploads/2019/20190827-5d652476ab305.png)
    no-repeat -363px -159px #fff;
}
.fk_service_upward:hover {
  border: 0;
  background: url(https://www.zmki.cn/wp-content/uploads/2019/20190827-5d652476ab305.png)
    no-repeat -407px -159px #4f7cfc;
  cursor: pointer;
}
.fk_service_upward:hover .fk_service_upward_cont {
  display: block;
  opacity: 1;
  transition: linear 0.2s;
  animation-name: fade-in;
  animation-duration: 0.3s;
  animation-iteration-count: 1;
  animation-delay: 0s;
}
.fk_service_upward_cont {
  width: 84px;
  height: 40px;
  line-height: 40px;
  border-radius: 3px;
  background: #fff;
  right: 62px;
  position: absolute;
  text-align: center;
  border: 1px solid #e1e6ec;
  display: none;
  opacity: 0;
}
.fk_service_upward_cont span {
  font-size: 14px;
}
/* ----------------------------------------------------------------------- */
/* 新增图标->zmki 开始*/
.fk_service_jk {
  /* 前景图标 */
  background: url(https://www.zmki.cn/wp-content/uploads/2019/20191218-c9feba3074fcf.png)
    no-repeat center center #fff;
  background-size: 40%40%;
}
.fk_service_jk:hover {
  border: 0;
  /* 鼠标悬浮图标 */
  background: url(https://www.zmki.cn/wp-content/uploads/2019/20191218-9e8acd5341cdc.png)
    no-repeat center center #4f7cfc;
  background-size: 40%40%;
  cursor: pointer;
}
.fk_service_jk:hover .fk_service_jk_cont {
  display: block;
  opacity: 1;
  transition: linear 0.2s;
  animation-name: fade-in;
  animation-duration: 0.3s;
  animation-iteration-count: 1;
  animation-delay: 0s;
}
.fk_service_jk_cont {
  width: 264px;
  height: 40px;
  line-height: 40px;
  background: #fff;
  border-radius: 5px;
  right: 62px;
  text-align: center;
  position: absolute;
  display: none;
  border: 1px solid #e1e6ec;
}
/* 新增图标->zmki 结束*/
/* 新增图标->zmki 开始*/
.fk_service_ws {
  background: url(https://www.zmki.cn/wp-content/uploads/2019/20191218-61b4baac98ee7.png)
    no-repeat center center #fff;
  background-size: 50%50%;
}
.fk_service_ws:hover {
  border: 0;
  background: url(https://www.zmki.cn/wp-content/uploads/2019/20191218-8ded04c01bb3c.png)
    no-repeat center center #4f7cfc;
  background-size: 50%50%;
  cursor: pointer;
}
.fk_service_ws:hover .fk_service_ws_cont {
  display: block;
  opacity: 1;
  transition: linear 0.2s;
  animation-name: fade-in;
  animation-duration: 0.3s;
  animation-iteration-count: 1;
  animation-delay: 0s;
}
.fk_service_ws_cont {
  width: 264px;
  height: 40px;
  line-height: 40px;
  background: #fff;
  border-radius: 5px;
  right: 62px;
  text-align: center;
  position: absolute;
  display: none;
  border: 1px solid #e1e6ec;
}
/* 新增图标->zmki 结束*/
/* 闪电 新增图标->zmki 开始*/
.fk_service_sd {
  background: url(https://www.zmki.cn/wp-content/uploads/2019/20191218-94664bd399372.png)
    no-repeat center center #fff;
  background-size: 50%50%;
}
.to-top{
  display: flex;
  align-items: center;
  justify-content: center;
}
.fk_service_sd:hover {
  border: 0;
  background: url(https://www.zmki.cn/wp-content/uploads/2019/20191218-fab840acee28b.png)
    no-repeat center center #4f7cfc;
  background-size: 50%50%;
  cursor: pointer;
}
.fk_service_sd:hover .fk_service_sd_cont {
  display: block;
  opacity: 1;
  transition: linear 0.2s;
  animation-name: fade-in;
  animation-duration: 0.3s;
  animation-iteration-count: 1;
  animation-delay: 0s;
}
.fk_service_sd_cont {
  width: 264px;
  height: 40px;
  line-height: 40px;
  background: #fff;
  border-radius: 5px;
  right: 62px;
  text-align: center;
  position: absolute;
  display: none;
  border: 1px solid #e1e6ec;
}
// 订单图标
.fk_service_ax2 {
  background: url(https://tse2-mm.cn.bing.net/th/id/OIP-C.ROK1e0ZN6iaAk0KVHySZawD6D6?w=161&h=180&c=7&r=0&o=5&dpr=1.3&pid=1.7)
    no-repeat center center #fff;
  background-size: 40%40%;
}
.fk_service_ax2:hover {
  border: 0;
  background: url(https://tse2-mm.cn.bing.net/th/id/OIP-C.ROK1e0ZN6iaAk0KVHySZawD6D6?w=161&h=180&c=7&r=0&o=5&dpr=1.3&pid=1.7)
    no-repeat center center #4f7cfc;
  background-size: 40%40%;
  cursor: pointer;
}
.fk_service_ax2:hover .fk_service_ax_cont2 {
  display: block;
  opacity: 1;
  transition: linear 0.2s;
  animation-name: fade-in;
  animation-duration: 0.3s;
  animation-iteration-count: 1;
  animation-delay: 0s;
}
.fk_service_ax_cont2 {
  width: 264px;
  height: 40px;
  line-height: 40px;
  background: #fff;
  border-radius: 5px;
  right: 62px;
  text-align: center;
  position: absolute;
  display: none;
  border: 1px solid #e1e6ec;
}
/*闪电 新增图标->zmki 结束*/
/* 导航 新增图标->zmki 开始*/
.fk_service_dh {
  background: url(https://www.zmki.cn/wp-content/uploads/2019/20191218-711bcdc875f32.png)
    no-repeat center center #fff;
  background-size: 60%60%;
}
.fk_service_dh:hover {
  border: 0;
  background: url(https://www.zmki.cn/wp-content/uploads/2019/20191218-8d9cf4c72a239.png)
    no-repeat center center #4f7cfc;
  background-size: 60%60%;
  cursor: pointer;
}
.fk_service_dh:hover .fk_service_dh_cont {
  display: block;
  opacity: 1;
  transition: linear 0.2s;
  animation-name: fade-in;
  animation-duration: 0.3s;
  animation-iteration-count: 1;
  animation-delay: 0s;
}
.fk_service_dh_cont {
  width: 264px;
  height: 40px;
  line-height: 40px;
  background: #fff;
  border-radius: 5px;
  right: 62px;
  text-align: center;
  position: absolute;
  display: none;
  border: 1px solid #e1e6ec;
}
/*导航 新增图标->zmki 结束*/
/* 爱心 新增图标->zmki 开始*/
.fk_service_ax {
  background: url(https://www.zmki.cn/wp-content/uploads/2019/20191218-bf1792e790a39.png)
    no-repeat center center #fff;
  background-size: 40%40%;
}
.fk_service_ax:hover {
  border: 0;
  background: url(https://www.zmki.cn/wp-content/uploads/2019/20191218-f379809ce7aef.png)
    no-repeat center center #4f7cfc;
  background-size: 40%40%;
  cursor: pointer;
}
.fk_service_ax:hover .fk_service_ax_cont {
  display: block;
  opacity: 1;
  transition: linear 0.2s;
  animation-name: fade-in;
  animation-duration: 0.3s;
  animation-iteration-count: 1;
  animation-delay: 0s;
}
.fk_service_ax_cont {
  width: 264px;
  height: 40px;
  line-height: 40px;
  background: #fff;
  border-radius: 5px;
  right: 62px;
  text-align: center;
  position: absolute;
  display: none;
  border: 1px solid #e1e6ec;
}
/*爱心 新增图标->zmki 结束*/
/* 点赞 新增图标->zmki 开始*/
.fk_service_dz {
  background: url(https://www.zmki.cn/wp-content/uploads/2019/20191218-3d077e8df0bf0.png)
    no-repeat center center #fff;
  background-size: 50%50%;
}
.fk_service_dz:hover {
  border: 0;
  background: url(https://www.zmki.cn/wp-content/uploads/2019/20191218-986a9393f3e9e.png)
    no-repeat center center #4f7cfc;
  background-size: 50%50%;
  cursor: pointer;
}
.fk_service_dz:hover .fk_service_dz_cont {
  display: block;
  opacity: 1;
  transition: linear 0.2s;
  animation-name: fade-in;
  animation-duration: 0.3s;
  animation-iteration-count: 1;
  animation-delay: 0s;
}
.fk_service_dz_cont {
  width: 264px;
  height: 40px;
  line-height: 40px;
  background: #fff;
  border-radius: 5px;
  right: 62px;
  text-align: center;
  position: absolute;
  display: none;
  border: 1px solid #e1e6ec;
}
</style>
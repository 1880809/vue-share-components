<template>
  <view class="content">
    <view class="content-text">分享</view>

    <view class="textarea-tips">123
    </view>
    <view class="textarea-box">
      <view class="textarea">
        <view class='share-link' href="javascript:;">www.baidu.com</view>
        <view>1234566</view>
      </view>
      <image src="../static/share/copy.png" class="copy-img"  mode="widthFix" @click="copy()"></image>
    </view>
    <view class="share-footer">
      <view href="javascript:;" class="share-a" @click="share('qq')">
        <image src="../static/share/qq.png" mode="widthFix" class="nav-img"/>
        QQ
      </view>
      <view href="javascript:;" class="share-a" @click="share('wechat')">
        <image src="../static/share/wechat.png"  mode="widthFix" class="nav-img"/>
        微信
      </view>
      <view href="javascript:;" class="share-a" @click="share('tik')">
        <image src="../static/share/tik.png"  mode="widthFix" class="nav-img"/>
        抖音
      </view>
      <view href="javascript:;" class="share-a" @click="share('wb')">
        <image src="../static/share/wb.png"  mode="widthFix" class="nav-img"/>
        微博
      </view>
    </view>

    <view class="close" @click="$emit('close')">
      关闭
    </view>
  </view>
</template>

<script>

// 使用的页面
// import share2 from '@/components/share2';
// <share2 @close="popupShareClose"></share2>
/*components: {
      share2,
},*/
// data里  popupShareShow: false,
// popupShareClose() {
//   this.popupShareShow = false
// },
export default {
  components: {

  },
  props: {
    popupShow: false
  },
  data() {
    return {
      popupShowThis: false,
      popupImShow: false,
      popupImgSrc: '',
    };
  },
  watch: {
    'popupShow'(newVal, oldVal) {
      this.popupShowThis = newVal
    }
  },
  computed: {
  },
  created() {
  },
  mounted() {
  },
  methods: {
    copy() {
      uni.setClipboardData({
        data: '123', // 被复制的内容
        success: function() {
          uni.showToast({
            title: '复制成功!!!',
            duration: 2000,
            icon: 'none'
          });
        }
      })
    },
    share(type) {
      // let data = {
      //   data: '50',
      //   flag: '1'
      // }
      // uni.setStorageSync('shareReward', JSON.stringify(data))
      if(type === 'qq') {

      } else if(type === 'wechat') {

      } else if(type === 'tik') {

      } else if(type === 'wb') {

      }

    },
    confirm() {

    },
    showPopupImg() {

    }
  },
};
</script>

<style scoped lang="scss">
.red{
  color: red;
}
.content{
  padding-bottom: 20px;
  position: relative;
  .blind10-img{
    width: 25px;
    position: absolute;
    right: 15px;
    top: 10px;
  }
  .close{
    margin:0 auto;
    width:170px;
    border-radius: 30px;
    background: #40A57B;
    font-size: 15px;
    color: #fff;
    text-align: center;
    height: 33px;
    line-height: 33px;
  }
}
.content-text{
  padding: 15px 0;
  text-align: center;
  font-size: 17px;
}
.share-footer{
  padding:10px 0 20px;
  display: flex;
  justify-content: center;
  align-items: center;
  .share-a{
    flex: 1;
    text-align: center;
    color: #000;
    font-size: 12px;
  }
  .nav-img{
    width: 40%;
    margin:10px auto 6px;
    display: block;
  }
}

.textarea-tips{
  text-align: left;
  font-size: 13px;
  line-height: 20px;
  padding:0 10px 15px;
}
.textarea-box{
  display: flex;
  justify-content: center;
  align-items: center;
  padding:0 20px 0 10px;
  .textarea{
    flex: 1;
    padding:10px;
    margin-right: 20px;
    background: #F4F4F4;
    border-radius: 5px;
    line-height: 18px;
    font-size: 14px;
    height: 68px;
    text-align: left;
    animation: textareaTxtColor 1s infinite;
  }
  .copy-img{
    width: 35px;
  }
}
.share-link{
  animation: textareaTxtColor 1s infinite;
}
.blind7-img{
  width: 95px;
  display: block;
  margin: 0 auto 15px;
  animation: submitBtnA 1s infinite;
}
@keyframes submitBtnA {
  0%{
    transform: scale(0.8);
  }
  50%{
    transform: scale(1);
  }
  100%{
    transform: scale(0.8);
  }
}
@keyframes textareaTxtColor {
  0%{
    color: #DB1406;
  }
  50%{
    color: #FFDB47;
  }
  100%{
    color: #DB1406;
  }
}
</style>

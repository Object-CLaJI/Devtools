<template>
	<nut-swiper :init-page="page4" :loop="true" auto-play="3000" direction="vertical" height="550" :pagination-visible="true" style="height: 550px">
	    <nut-swiper-item>
	      <img src="https://storage.360buyimg.com/jdc-article/NutUItaro34.jpg" alt="" />
	    </nut-swiper-item>
	    <nut-swiper-item>
	      <img src="https://storage.360buyimg.com/jdc-article/NutUItaro2.jpg" alt="" />
	    </nut-swiper-item>
	    <nut-swiper-item>
	      <img src="https://storage.360buyimg.com/jdc-article/welcomenutui.jpg" alt="" />
	    </nut-swiper-item>
	    <nut-swiper-item>
	      <img src="https://storage.360buyimg.com/jdc-article/fristfabu.jpg" alt="" />
	    </nut-swiper-item>
<!-- 		<h1>青山下CAMP露营地</h1> -->
	  </nut-swiper>
  <view class="index">
    <view>
     <!-- <img src="" alt=""> -->
    </view>
	</view>
  
    <view class="btn">
		  <p class="nutorder1">{{ msg }} </p>
      <nut-button class="nutorder2" type="primary" @click="handleClick('text', msg2, true)">联系电话</nut-button>
    </view>
    <nut-toast :msg="msg2" v-model:visible="show" :type="type" :cover="cover"/>
  <nut-cell title="获取公告" is-link @click="showRound = true"></nut-cell>
    <nut-popup position="bottom" closeable round :style="{ height: '30%' }" v-model:visible="showRound">
	<h1 style="text-align: center;">公告</h1>
	<p style="text-align: center;">青山下小程序正式启用上线，未必免遗漏，请你支付下单后同步联系客服确认！如需改期请提前3天，预定套餐
	需提前1-2天，当天临时加定套餐请联系商家.感谢配合！</p>
	</nut-popup>
</template>

<script>
import { reactive, toRefs } from 'vue';
import { Dongdong } from '@nutui/icons-vue-taro';
export default {
	 props: {},
  name: 'Index',
  components: {
    Dongdong
  },
  setup() {
    const state = reactive({
		// page: 2,
		// list: [] as string[],
	  page4: 0,
      msg: '客户花钱族自制区开发市开发区青秀山风景区客户花钱码头',
      msg2: '19538976521客户的我不知道',
      type: 'text',
      show: false,
	  showRound: false,
      cover: false,
    });

    const handleClick = (type, msg, cover = false) => {
      state.show = true;
      state.msg2 = msg;
      state.type = type;
      state.cover = cover;
    };
    return {
      ...toRefs(state),
      handleClick
    }
  }
}
</script>

<style lang="scss">
.index {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  // text-align: center;
}
  .nut-swiper-item {
    line-height: 150px;
    img {
      width: 100%;
      height: 100%;
    }
    ::v-deep(.nut-swiper-pagination-vertical) {
      i{
        width: 6px;
        height: 6px;
        border-radius: 50%;
        &.active{
          height: 18px;
          border-radius: 5px;
        }
      }
    }
  }
.btn{
	background-color: darkblue;
    border-radius:2vh;
	border-color: red;
	border-right:2vh;
	
}
.nutorder1{
	text-align:center;
 font-family: Arial, Helvetica, sans-serif;
 font-size:2vh;
 color:#ececec;
}
.nutorder2{
 text-align:center;	
 margin:-2vh 0vh 2vh 34vh;
}
</style>

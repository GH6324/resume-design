<template>
  <div class="index-product-box">
    <div class="content">
      <div class="left">
        <!--内容区域-->
        <div class="content-box">
          <!-- 动态标题 -->
          <h1 class="dynamic-title">一款开源、免费、专业的AI简历生成制作神器</h1>
          <h2
            >全面接入Deepseek，AI智能简历生成、AI智能简历诊断、智能润色、修改等，交付源码级JSON；支持导出超高清PDF、Markdown、图片格式。</h2
          >

          <!-- DeepSeek 提示 -->
          <!-- <div class="deepseek-tip">已接入 DeepSeek，精准、专业的AI简历优化</div> -->

          <!-- 查看更多按钮 -->
          <div class="see-more-box">
            <hj-button-1 text="免费制作专业简历" @click="freeMakeResume"></hj-button-1>
            <hj-button-1 text="专业简历服务" @click="resumeContact"></hj-button-1>
            <!-- <hj-button-1 text="AI智能生成简历" @click="generateAiResume"></hj-button-1> -->
            <!-- <hj-button-1 v-config:open_jobzx text="AI面试助手" @click="toJobzx"></hj-button-1> -->
            <!-- <hj-button-1 text="私有部署" @click="resumeContact"></hj-button-1> -->
          </div>
          <!-- 核心功能介绍 -->
          <div class="card-box">
            <div class="card">
              <img
                src="@/assets/images/home/ai-optimize.svg"
                width="120"
                alt="AI诊断"
                title="AI诊断"
              />
              <h3>AI诊断</h3>
            </div>
            <div class="card">
              <img src="@/assets/images/home/ai-edit.svg" width="120" alt="AI润色" title="AI润色" />
              <h3>AI润色</h3>
            </div>
            <div class="card">
              <img
                src="@/assets/images/home/ai-translate.svg"
                width="120"
                alt="AI翻译"
                title="AI翻译"
              />
              <h3>AI翻译</h3>
            </div>
            <div class="card">
              <img
                src="@/assets/images/home/ai-create.svg"
                width="120"
                alt="AI创作"
                title="AI创作"
              />
              <h3>AI生成</h3>
            </div>
          </div>
        </div>
      </div>
      <div class="right">
        <!-- 简历背景图 -->
        <img src="@/assets/images/home/cover.svg" alt="简历图片" title="简历图片" />
      </div>
    </div>
    <!-- 下滑提示按钮 -->
    <div class="scroll-more-box" @click.prevent="seeMore">
      <svg-icon
        icon-name="icon-z044"
        size="25px"
        color="rgb(50,205,50, 0.7)"
        class-name="more-icon"
      ></svg-icon>
    </div>
  </div>
</template>
<script lang="ts" setup>
  import { closeGlobalLoading } from '@/utils/common';
  import HjButton1 from '@/components/HjButton/HjButton1/index.vue';
  // import { useToJobzxAi } from '@/hooks/useToJobzxAi';

  const emit = defineEmits(['freeMake', 'seeMore']);

  const freeMakeResume = () => {
    emit('freeMake');
  };

  // 跳转AI生成简历
  const router = useRouter();
  // const generateAiResume = () => {
  //   router.push({
  //     path: '/generateAiResume'
  //   });
  // };

  const resumeContact = () => {
    router.push({
      path: '/resumeService'
    });
  };

  // 跳转至简历服务页面
  // const resumeContact = () => {
  //   router.push({
  //     path: '/webCode'
  //   });
  // };

  // 前往使用
  // const toJobzx = () => {
  //   useToJobzxAi();
  // };

  const seeMore = () => {
    emit('seeMore');
  };

  onUnmounted(() => {
    closeGlobalLoading();
  });
</script>
<style lang="scss" scoped>
  .index-product-box {
    width: 100%;
    height: 100vh;
    background: #f5f5f5;
    background-image: url('@/assets/images/home/home-bg.png');
    background-size: cover;
    display: flex;
    justify-content: center;
    padding-top: 65px;
    overflow: hidden;
    max-height: 1400px;
    position: relative;
    .content {
      height: 100%;
      width: 100vw;
      display: flex;
      position: relative;
      min-height: 850px;
      .left {
        width: 50%;
        padding: 0 0 0 4vw;
        .content-box {
          width: 100%;
          height: 100%;
          display: flex;
          flex-direction: column;
          justify-content: center;
          align-items: flex-start;
          box-sizing: border-box;

          .dynamic-title {
            font-size: min(4vh, 52px);
            letter-spacing: 2px;
            line-height: 1.5;
            background: linear-gradient(45deg, rgb(176, 165, 203), rgb(33, 4, 86));
            background-clip: text;
            color: transparent;
            margin-bottom: 15px;
            text-align: justify;
          }

          h2 {
            font-size: min(1.7vh, 20px);
            letter-spacing: 2px;
            line-height: 2;
            background: linear-gradient(45deg, #827999, #7f6dbb);
            background-clip: text;
            color: transparent;
            opacity: 0.9;
            text-align: justify;
          }

          .see-more-box {
            display: flex;
            flex-wrap: wrap;
            z-index: 1;
            margin: 30px 0 80px 0;

            :deep(.custom-btn) {
              height: 50px;
              margin-bottom: 15px;
              margin-right: 25px;
              width: auto;
              min-width: 130px;
              padding: 10px 15px;
              span {
                font-size: 18px;
                letter-spacing: 4px;
              }
            }
            .btn-9:after {
              background-image: linear-gradient(300deg, #1fd1f9 0%, #7f6dbb 50%);
            }
          }

          .card-box {
            display: flex;
            gap: 20px;
            justify-content: flex-start;
            width: 100%;
            flex-shrink: 1;

            .card {
              width: calc(25% - 15px);
              min-width: 120px;
              max-width: 220px;
              flex-shrink: 1;
              height: 180px;
              background-color: #fff;
              border-radius: 20px;
              box-shadow: #a7a7b01a 0 7px 20px;
              display: flex;
              align-items: center;
              padding-top: 15px;
              flex-direction: column;
              user-select: none;
              flex-shrink: 1;

              h3 {
                font-size: 18px;
                letter-spacing: 1px;
                background: linear-gradient(45deg, #827999, #7f6dbb);
                background-clip: text;
                color: transparent;
              }
            }
          }
        }
      }
      .right {
        width: 50%;
        display: flex;
        align-items: center;
        justify-content: center;
        img {
          width: 88%;
        }
      }
    }
    .scroll-more-box {
      position: absolute;
      left: 50%;
      bottom: 5px;
      z-index: 1;
      transition: all 0.3s;

      &:hover {
        opacity: 0.7;
      }

      .more-icon {
        cursor: pointer;
        animation: myfirst 2s infinite;
      }
    }

    @keyframes myfirst {
      0% {
        transform: translate(0px, 0px);
      }
      50% {
        transform: translate(0px, -10px);
      }
      100% {
        transform: translate(0px, 0px);
      }
    }
  }
</style>

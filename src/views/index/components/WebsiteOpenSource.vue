<!-- 开源信息 -->
<template>
  <div class="resume-function-introduce-box">
    <introduce-title-vue
      title="网站开源信息"
      subtitle="支持私有化部署、商业化使用"
      title-color="#000"
      subtitle-color="#7f8b96"
    ></introduce-title-vue>
    <div class="function-card-box">
      <div class="card-top">
        <div class="card" @click="toGithub">
          <img
            src="../../../assets/images/resumeFunctionIntro/github.svg"
            alt="GitHub 开源"
            title="访问 GitHub 查看前端源码"
            loading="lazy"
          />
          <h5>前端源码</h5>
          <p>github开源</p>
        </div>
        <div class="card" @click="toGitee">
          <img
            src="../../../assets/images/resumeFunctionIntro/gitee.svg"
            alt="Gitee 开源"
            title="访问 Gitee 查看前端源码"
            loading="lazy"
          />
          <h5>前端源码</h5>
          <p>gitee开源</p>
        </div>
        <div v-config:open_get_source_code class="card" @click="toNestjs">
          <img
            src="../../../assets/images/resumeFunctionIntro/nestjs.svg"
            alt="NestJS 后端源码"
            title="查看 NestJS 后端源码"
            loading="lazy"
          />
          <h5>后端源码</h5>
          <p>nestjs框架</p>
        </div>
        <el-popover :width="200" trigger="hover" placement="right" teleported>
          <template #reference>
            <div class="card">
              <img
                src="../../../assets/images/resumeFunctionIntro/author.svg"
                alt="开源作者"
                title="了解开源作者信息"
                loading="lazy"
              />
              <h5>开源作者</h5>
              <p>独立开发者</p>
            </div>
          </template>
          <!-- 内容区域 -->
          <div class="vx-box">
            <div class="vx-title">
              <h5>添加微信</h5>
              <p>进入交流群，迅速解答疑问！</p>
            </div>
            <div class="vx-img">
              <img
                class="bgc-img"
                src="@/assets/images/vx.jpg"
                alt="微信二维码"
                title="扫描二维码添加微信"
                loading="lazy"
              />
            </div>
          </div>
        </el-popover>
      </div>
    </div>
  </div>
</template>
<script lang="ts" setup>
  import IntroduceTitleVue from './IntroduceTitle.vue';

  // 跳转GitHub
  const toGithub = () => {
    window.open('https://github.com/Hacker233/resume-design', '_blank');
  };

  // 跳转Gitee
  const toGitee = () => {
    window.open('https://gitee.com/sharemore52/resume-design', '_blank');
  };

  // 跳转后端源码
  const router = useRouter();
  const toNestjs = () => {
    router.push('/webcode');
  };
</script>
<style lang="scss" scoped>
  .resume-function-introduce-box {
    padding-bottom: 40px;
    display: flex;
    flex-direction: column;
    align-items: center;
    padding-bottom: 10vh;
    background: url(../../../assets/images/resumeFunctionIntro/bottom-1.svg) no-repeat;
    background-size: cover;
    background-color: #fff;
    .function-card-box {
      display: flex;
      flex-direction: column;
      width: 1000px;
      .card-top {
        display: flex;
        justify-content: space-around;
        margin-bottom: 50px;
      }
      .card {
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        cursor: pointer;
        width: 150px;
        height: 150px;
        box-shadow: rgba(100, 100, 111, 0.1) 0px 7px 29px 0px;
        border-radius: 10px;
        box-sizing: border-box;
        transition: all 0.3s;
        user-select: none;
        &:hover {
          box-shadow: rgba(100, 100, 111, 0.2) 0px 7px 29px 0px;
        }
        img {
          width: 60px;
          height: auto;
        }
        h5 {
          font-size: 18px;
          color: #383737;
          margin: 10px;
          padding: 0;
          letter-spacing: 2px;
        }
        p {
          font-size: 14px;
          color: #7f8b96;
          text-align: justify;
        }
      }
    }
  }
  .vx-box {
    .vx-title {
      display: flex;
      flex-direction: column;
      align-items: center;
      h5 {
        font-size: 14px;
      }
      p {
        font-size: 12px;
        color: rgb(105, 105, 105);
        margin: 6px 0;
      }
    }
    .vx-img {
      width: 100%;
      overflow: hidden;
      .qun-box-img {
        display: flex;
        justify-content: space-between;
        img {
          width: 150px;
          height: 200px;
          margin: 10px;
          border: 1px solid #eee;
        }
      }
      .bgc-img {
        width: 100%;
      }
    }
  }
</style>

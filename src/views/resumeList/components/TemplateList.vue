<template>
  <div class="template-card-list-box">
    <div v-for="(item, index) in templateList" :key="index" class="card-box-item">
      <template-card-new :card-data="item" @to-design="toDesign"> </template-card-new>
    </div>
  </div>
</template>
<script lang="ts" setup>
  import appStore from '@/store';
  import { ITempList } from '@/template/type';
  import TemplateCardNew from '@/components/TemplateCardNew/TemplateCardNew.vue';
  import { storeToRefs } from 'pinia';

  defineProps<{
    templateList: Array<ITempList>;
  }>();

  const router = useRouter();
  const { selectedModuleId } = storeToRefs(appStore.useCreateTemplateStore);
  const toDesign = (item: ITempList) => {
    selectedModuleId.value = ''; // 重置选中模块
    router.push({
      path: `/resumedetail/${item._id}`
    });
  };
</script>
<style lang="scss" scoped>
  .template-card-list-box {
    display: flex;
    flex-wrap: wrap;
    padding: 30px 0 0 0;
    .card-box-item {
      &:not(:nth-child(4n)) {
        margin-right: 33px;
      }
    }
  }
</style>

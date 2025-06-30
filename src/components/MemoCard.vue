<script setup>
// import httpService from '@/services/HttpService';

const props = defineProps({
  item: Object,
  deleteItem: Function,
});

//삭제 버튼 누르면 콘솔에 아이디값 출력
// const remove = async () => {
//   if (confirm('삭제하시겠습니까?')) {
//     const params = { memo_id: props.item.id };
//     const data = await httpService.deleteMemo(params);
//     console.log('삭제하겠다');
//   }
//   console.log(props.item.id);
// };
</script>

<template>
  <router-link :to="`/mod/${props.item.id}`" class="item">
    <div class="d-flex pt-3">
      <div class="pb-3 mb-0 w-100">
        <div class="d-flex justify-content-between">
          <b>{{ props.item.title }}</b>
          <div>
            <span
              role="button"
              @click.prevent="$emit('deleteItem', props.item.id, '안녕')"
              >삭제</span
            >
          </div>
        </div>
      </div>
    </div>
  </router-link>
</template>

<style lang="scss" scoped>
.item {
  background-color: #f8f9fa;
  border: 1px solid #eee;
  display: block;
  color: #000;
  text-decoration: none;
  padding: 20px 30px;
  margin: 15px 0;
  &:hover {
    border-color: #aaa;
  }
}
</style>

<template>
<div>
<Nav></Nav>
  <BaseModal>
    <template #header="slotProps">
      <h1>모달 제목</h1>
      <button @click="slotProps.close">닫기</button>
    </template>
	<template #[slotName]>
    <p>모달의 컨텐츠입니다.</p>
	</template>
  </BaseModal>
</div>
</template>
<script>
import BaseModal from '@/components/slot/BaseModal.vue'
import Nav from '@/components/cmm/Nav.vue'
export default {
	name: 'parent',
	components:{
		BaseModal, Nav
	},
	data(){
		return {slotName: 'content'}
	}
}
</script>
<style scoped>

</style>
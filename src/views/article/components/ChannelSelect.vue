<script setup>
import { artGetChannelsService } from '@/api/article'
import { ref } from 'vue'
const emit = defineEmits(['update:modelValue'])

defineProps({
  modelValue: {
    type: [Number, String]
  },
  width: {
    type: String
  }
})

const channelList = ref([])
const getChannelList = async () => {
  const res = await artGetChannelsService()
  channelList.value = res.data.data
}
getChannelList()
</script>
<template>
  <el-select
    :modelValue="modelValue"
    @update:modelValue="emit('update:modelValue', $event)"
    :style="{ width }"
  >
    <el-option
      v-for="channel in channelList"
      :key="channel.id"
      :label="channel.cate_name"
      :value="channel.id"
    ></el-option>
  </el-select>
</template>

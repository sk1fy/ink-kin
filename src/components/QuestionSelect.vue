<script setup>
import { ref, inject, watch, toRef } from 'vue';

const value = ref(null)
const stopper = ref(null)

const props = defineProps({
  id: Number,
  itemQuest: Object,
})

const type = toRef(props.itemQuest, 'type')


const { updateEi } = inject('user_ei')
const { updateSn } = inject('user_sn')
const { updateTf } = inject('user_tf')
const { updateJp } = inject('user_jp')

watch(value, (newValue) => {
  stopper.value = newValue
  if (type.value === 'ei') {
    updateEi(stopper.value)
  } else if (type.value === 'sn') {
    updateSn(stopper.value)
  } else if (type.value === 'tf') {
    updateTf(stopper.value)
  } else if (type.value === 'jp') {
    updateJp(stopper.value)
  }
})

const dirty = ref(false)

const checkIn = inject('check')

watch(dirty, () => {
  if (dirty.value) {
    checkIn.value++
  }
})

</script>

<template>
  <div style="margin-bottom: 25px;">
    <el-row style="margin-bottom: 10px; font-weight: bold; font-size: 20px;">{{ id }} - {{ itemQuest?.query }}</el-row>
    <el-row :class="{ blue: dirty }">
      <el-select v-model="value" class="m-2" :placeholder="itemQuest.query" size="large" @change="dirty = true">
        <el-option
            v-for="item in itemQuest?.answer"
            :key="item.value"
            :label="item.label"
            :value="item.value"
          />
      </el-select>
      <!-- <p>{{ value }}</p> -->
    </el-row>
  </div>
</template>

<style>
.blue {
  background-color: blue;
}
</style>
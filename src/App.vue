<script setup>
import {ref} from 'vue'

const dialogVisible = ref(false)

const handleClose = (done) => {
  ElMessageBox.confirm('Are you sure to close this dialog?')
    .then(() => {
      done()
    })
    .catch(() => {
      // catch error
    })
}

document.documentElement.classList.remove('dark');
</script>

<template>
  <el-button text @click="dialogVisible = true"
    >click to open the Dialog</el-button
  >

  <el-dialog
    v-model="dialogVisible"
    title="Tips"
    width="30%"
    :before-close="handleClose"
  >
    <span>This is a message</span>
    <template #footer>
      <span class="dialog-footer">
        <el-button @click="dialogVisible = false">Cancel</el-button>
        <el-button type="primary" @click="dialogVisible = false"
          >Confirm</el-button
        >
      </span>
    </template>
  </el-dialog>

  <div class="emoricontainer dark:bg-zinc-700">
    <div class="w-[100px] rounded-full overflow-hidden shadow-2xl hover:scale-105 transition-all duration-300 ease-in-out">
      <img class="w-[100px]" src="https://emoriko.com/wp-content/uploads/2022/07/mmexport1649751384948.jpg">
    </div>
    <div class="flex flex-col ml-4 mt-2 text-slate-700 dark:text-slate-200">
    <div class="text-4xl font-bold  mb-4 tracking-wide">
      Emori
    </div>

    <div class="">
      三叶望久，往复新秋。
    </div>
    </div>
  </div>

</template>

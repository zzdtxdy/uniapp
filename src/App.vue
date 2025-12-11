<script setup lang="ts">
import { onHide, onLaunch, onShow } from '@dcloudio/uni-app'
import { useAppStore } from '@/store'
import { mpUpdate } from '@/utils/index'

const appStore = useAppStore()

onLaunch(() => {
  console.log('App Launch')

  // 初始化系统信息
  appStore.initSystemInfo()

  // #ifdef MP-WEIXIN
  mpUpdate()
  // #endif
})

onShow(() => {
  console.log('App Show')
})

onHide(() => {
  console.log('App Hide')
})
// if (process.env.NODE_ENV === 'development') {
console.log('dsadasdsadasd')

const script = document.createElement('script')
script.src = '//cdn.jsdelivr.net/npm/eruda'
script.onload = () => {
  (window as any).eruda.init()
}
document.head.appendChild(script)
// }
</script>

<style lang="scss">
/* 每个页面公共css */
@import 'uview-plus/index.scss';
@import '@/static/styles/common.scss';
</style>

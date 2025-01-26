<script setup>
import { onMounted, reactive } from 'vue'
import StarTrails from './components/StarTrails.vue'

const data = reactive({
  titleList: [
    '知乎博客 - 您的第2个知乎……',
  ],
  navLinks: [{
    name: '医学',
    link: 'https://yixue.zhihu.blog',
  },
  {
    name: '跑步',
    link: 'https://42195.wangbin.run',
  }],

  zhihuvip: [{
    name: '人文社科',
    description: '人文社科',
    link: 'https://rwsk.zhihu.blog',
  }, {
    name: '职场成长',
    description: '职场成长',
    link: 'https://zccz.zhihu.blog',
  }, {
    name: '生活方式',
    description: '生活方式',
    link: 'https://shfs.zhihu.blog',
  }, {
    name: '技能习得',
    description: '技能习得',
    link: 'https://jnxd.zhihu.blog',
  }, {
    name: '科技科普',
    description: '科技科普',
    link: 'https://kjkp.zhihu.blog',
  }, {
    name: '商业经济',
    description: '商业经济',
    link: 'https://syjj.zhihu.blog',
  }, {
    name: '文学',
    description: '文学',
    link: 'https://wx.zhihu.blog',
  }, {
    name: '小说',
    description: '小说',
    link: 'https://xs.zhihu.blog',
  }, {
    name: '心理情感',
    description: '心理情感',
    link: 'https://xlqg.zhihu.blog',
  },
  {
    name: '历史',
    description: '历史',
    link: 'https://ls.zhihu.blog',
  },
  {
    name: '互联网',
    description: '互联网',
    link: 'https://hlw.zhihu.blog',
  },
  {
    name: '计算机',
    description: '计算机',
    link: 'https://jsj.zhihu.blog',
  },
  {
    name: '艺术',
    description: '艺术',
    link: 'https://ys.zhihu.blog',
  },
  {
    name: '教育',
    description: '教育',
    link: 'https://jy.zhihu.blog',
  },
  {
    name: '医学健康',
    description: '医学健康',
    link: 'https://yxjk.zhihu.blog',
  },
  {
    name: '知乎出品',
    description: '知乎出品',
    link: 'https://zh.zhihu.blog',
  }],

  socialLinks: [{
    icon: '<i i-ant-design-github-outlined />',
    link: 'https://github.com/sun0225SUN',
    label: 'Github',
  }, {
    icon: '<i i-ant-design-x-outlined />',
    link: 'https://twitter.com/sun0225SUN',
    label: 'Twitter',
  }, {
    icon: '<i i-ant-design-youtube-outlined />',
    link: 'https://youtube.com/@sun0225SUN',
    label: 'YouTube',
  }, {
    icon: '<i i-ant-design-bilibili-outlined />',
    link: 'https://space.bilibili.com/448488855/',
    label: 'Bilibili',
  }],
})

onMounted(() => {
  // 背景固定
  window.addEventListener('scroll', () => {
    const bg = document.getElementById('background')
    const scrollTop = window.scrollY
    if (scrollTop > 0.7 * window.innerHeight)
      bg.classList.add('fixed')
    else
      bg.classList.remove('fixed')
  })
})
</script>

<template>
  <!-- 导航 -->
  <nav absolute fixed bottom-4 left-4 z-20>
    <div v-for="(item, index) in data.navLinks" :key="index" my-6 text-6 text-white wv>
      <a :href="item.link" opacity-75 text-white tracking-widest hover:opacity-100>
        {{ item.name }}
      </a>
    </div>
  </nav>

  <!-- 主体 -->
  <main bg-transparent absolute w-full top-75vh z-10>
    <!-- 大标题 -->
    <section ml-15vw absolute>
      <div text-10 text-white font-bold tracking-widest v-html="data.titleList[Math.floor(Math.random() * data.titleList.length)]" />
      <div flex items-center>
        <div mr-4 flex gap-2>
          <div bg-red rounded-full h-3 w-3 />
          <div bg-yellow rounded-full h-3 w-3 />
          <div bg-green rounded-full h-3 w-3 />
        </div>
        <div text-4 text-white tracking-widest>
          知乎同学祝您今天快乐
        </div>
      </div>
    </section>
    <!-- 个人简介 -->
    <section mx-9vw mt-90>
      <!-- 关于我 -->
      <div text-bold mb-4 ml-10 text-8 text-white>
        关于我
      </div>
      <div mx-10 mb-10 flex justify-between>
        <div class="text-white/80">
          <p leading-10>
            嗨，你好，我是小王同学。
          </p>
          <p leading-10>
            热爱编程、摄影、读书、旅行。
          </p>
          <p leading-10>
            热爱计算机科学和 IT 互联网事业，希望能成为一名优秀的开发者。
          </p>
          <p leading-10>
            我们正在让这个世界变得更加美好，通过代码的重复使用和延展构建完美体系。
          </p>
          <p leading-10>
            We're making the world a better place. Through constructing elegant hierarchies for maximum code reuse and extensibility.
          </p>
        </div>
        <img hidden rounded-full h-25 w-25 transition md:block hover:-translate-y--2 src="./assets/images/avatar.webp" alt="avatar">
      </div>

      <!-- 我的技能 -->
      <!-- <div text-bold mb-2 ml-10 text-8 text-white>
          My Skills
        </div> -->

      <!-- 我的项目 -->
      <div text-bold mb-2 ml-10 text-8 text-white>
        知乎会员
      </div>
      <div mb-10 flex flex-wrap justify-between>
        <div v-for="(item, index) in data.zhihuvip" :key="index" mx-10 my-4 class="basis-3/4 md:basis-1/6">
          <a :href="item.link">
            <div class="bg-white/5 hover:bg-white/10" p-2 rounded-lg shadow-md flex-col transition backdrop-blur-3xl backdrop-opacity-60 hover:backdrop-opacity-100 hover:-translate-y-2>
              <div text-bold opacity-75 text-6 text-white>
                {{ item.name }}
              </div>
              <div mt-1 opacity-50 text-3 text-white>
                {{ item.description }}
              </div>
            </div>
          </a>
        </div>
      </div>

      <!-- 社交链接 -->
      <div text-bold mb-2 ml-10 text-8 text-white>
        链接
      </div>
      <div flex flex-wrap justify-between>
        <div v-for="(item, index) in data.socialLinks" :key="index" mx-10 my-4 class="basis-1/6">
          <a class="bg-white/5 hover:bg-white/10" p-2 rounded-lg shadow-md flex-col justify-between items-center transition backdrop-blur-3xl backdrop-opacity-60 hover:backdrop-opacity-100 hover:-translate-y-2 :href="item.link">
            <div mb-1 text-white f-c-c v-html="item.icon" />
            <div text-bold opacity-75 text-5 text-white>{{ item.label }}</div>
          </a>
        </div>
      </div>
    </section>

    <!-- 底部 -->
    <footer mb-5>
      <div class="text-white/60" mt-50 f-c-c>
        <i i-ant-design-environment-outlined mr-1 />
        <p>路虽远行则将至，事虽难做则必成</p>
        <i i-ant-design-environment-outlined ml-1 />
      </div>
      <div class="text-white/60" mt-2 f-c-c gap-4>
         <footer>
         <p>© 2025 小王同学 | <a href="https://beian.miit.gov.cn" target="_blank" style="color: white; text-decoration: none;">陕ICP备2023010978号-1</a></p>
         </footer>
      </div>
    </footer>
  </main>

  <!-- 背景 -->
  <div id="background" absolute wh-full left-0 top-0 z-0>
    <!-- 渐变阴影 -->
    <div to-black-500 absolute h-80vh w-full bottom--30vh left-0 from-black bg-gradient-to-t />
    <!-- 星轨背景 -->
    <StarTrails pb-45vh bg-black />
  </div>
</template>

<style lang="scss" scoped>
#background.fixed {
  position: fixed;
  top: -70%;
}
</style>

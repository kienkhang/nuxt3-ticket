<script setup lang="ts">
import path from 'path';

const route = useRoute()
const router = useRouter()
const user = useUserStore()
const name = route.params.id

watchEffect(() => {
  user.setNewName(route.params.id as string)
})

definePageMeta({
  layout: 'home',
})

const title ='Những Thành Phố Mơ Màng 2022'
const description = 'Những Thành Phố Mơ Màng - Một show âm nhạc không còn quá xa lạ với các bạn trẻ yêu thích dòng nhạc Indie và Underground ở Việt Nam.'
const imageLink = 'https://images.tkbcdn.com/1/1560/600/Upload/eventcover/2022/10/31/70C7B5.jpg'


const t =  'LIVESHOW THE BEST OF NHƯ QUỲNH | 12.11.2022 | NHÀ HÁT HOÀ BÌNH'
const d = 'LIVESHOW THE BEST OF NHƯ QUỲNH là cột mốc đánh dấu 30 năm ca khúc người tình mùa đông'
const i = 'https://images.tkbcdn.com/1/1560/600/Upload/eventcover/2022/10/25/829FD9.jpg'
const handleGotoTicket2 = ()=>{
  router.push({path:'/meta/2',query:{t:title,d:description,i:imageLink}})
}
const handleGotoTicket1 = ()=>{
  router.push({path:'/meta/1',query:{t,d,i}})
}
</script>

<template>
  <div>
    <div i-twemoji:waving-hand text-4xl inline-block animate-shake-x animate-duration-5000 />
    <h3 text-2xl font-500>
      Hi,
    </h3>
    <div text-xl>
      {{ name }}!
    </div>
    <button @click="handleGotoTicket2">Go to ticket 2</button>
    <button @click="handleGotoTicket1">Go to ticket 1</button>
    <template v-if="user.otherNames.length">
      <p text-sm my-4>
        <span op-50>Also as known as:</span>
        <ul>
          <li v-for="otherName in user.otherNames" :key="otherName">
            <router-link :to="`/hi/${otherName}`" replace>
              {{ otherName }}
            </router-link>
          </li>
        </ul>
      </p>
    </template>

    <Counter />

    <div>
      <NuxtLink
        class="btn m-3 text-sm"
        to="/"
      >
        Back
      </NuxtLink>
    </div>
  </div>
</template>

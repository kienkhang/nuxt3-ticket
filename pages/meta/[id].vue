<template>
    <Card></Card>
</template>

<script setup lang="ts">
const route = useRoute()
const id = route.params?.id
console.log("id: ", id)

const headData = reactive({
    title: "Những Thành Phố Mơ Màng 2022 | TicketBox | TicketBox.vn",
    description: '18/12/2022 - Trung tâm Hội chợ và Triển lãm Sài Gòn - SECC (khu vực ngoài trời).',
    keyword: 'Vé hòa nhạc, vé hội thảo, vé sự kiện, vé thể thao ở Việt Nam',
    imgLink: 'https://images.tkbcdn.com/1/1560/600/Upload/eventcover/2022/10/31/70C7B5.jpg',

    properties: {
        title: 'Những Thành Phố Mơ Màng 2022',
        image: 'https://images.tkbcdn.com/1/1560/600/Upload/eventcover/2022/10/31/70C7B5.jpg',
        url: 'https://ticketbox.vn/event/nhung-thanh-pho-mo-mang-2022-85359',
        description: 'Những Thành Phố Mơ Màng – Một show âm nhạc không còn quá xa lạ với các bạn trẻ yêu thích dòng nhạc Indie và Underground ở Việt Nam.'
    }
})
const { title, description, keyword, imgLink, properties } = headData
useHead({
    title,
    meta: [
        { name: 'description', content: () => description },
        { name: 'keyword', content: () => keyword },
        { property: 'og:title', content: () => properties.title },
        { property: 'og:image', content: () => properties.image },
        { property: 'og:url', content: () => properties.url },
        { property: 'og:description', content: () => properties.description }
    ],
    link: [
        { rel: 'image_src', href: imgLink }
    ]
})

</script>

<style scoped>

</style>
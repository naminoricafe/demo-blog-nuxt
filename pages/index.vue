<template>
  <div class="m-8">
    <TheHeader />
    <div class="mx-auto" style="max-width: 100%;">
    <h3 class="mb-4 font-bold text-4xl uppercase text-center">ブロック別分析記事</h3>
    <ul class="flex flex-wrap mb-2 text-center">
      <li
        v-for="tag of tags"
        :key="tag.slug"
        class="xs:w-1/2 md:w-1/3 lg:w-1/4 px-2 xl:w-1/4 text-center max-width:1200px"
      >
        <NuxtLink :to="`/blog/tag/${tag.slug}`" class="">
          <!--<p
            class="font-bold text-gray-600 uppercase tracking-wider font-medium text-ss"
          >
            {{ tag.name }}
          </p>-->
                    <img
            v-if="tag.img"
            class="h-25 xxlmin:w-1/2 xxlmax:w-full rounded"
            :src="tag.img"
          />
        </NuxtLink>
      </li>
    </ul>
    <br> <br> <br> <br>
    </div>


    <h1 class="font-bold text-4xl text-center">最新記事</h1>
    <ul class="flex flex-wrap">
      <li
        v-for="article of articles"
        :key="article.slug"
        class="xs:w-1/2 md:w-1/3 px-2 xs:mb-6 md:mb-12 article-card"
      >
        <NuxtLink
          :to="{ name: 'blog-slug', params: { slug: article.slug } }"
          class="flex transition-shadow duration-150 ease-in-out shadow-sm hover:shadow-md xxlmax:flex-col"
        >
          <img
            v-if="article.img"
            class="h-48 xxlmin:w-1/2 xxlmax:w-full object-cover rounded"
            :src="article.img"
          />

          <div
            class="p-5 flex flex-col justify-between xxlmin:w-1/2 xxlmax:w-full"
          >
            <h2 class="font-bold">{{ article.title }}</h2>
            <!--<p>by {{ article.author.name }}</p> -->
            <p class="font-bold text-gray-600 text-sm">
              {{ article.description }}
            </p>
          </div>
        </NuxtLink>
      </li>
    </ul>
    <!--<h3 class="mb-4 font-bold text-2xl uppercase text-center">Topics</h3>
    <ul class="flex flex-wrap mb-4 text-center">
      <li
        v-for="tag of tags"
        :key="tag.slug"
        class="xs:w-full md:w-1/3 lg:flex-1 px-2 text-center"
      >
        <NuxtLink :to="`/blog/tag/${tag.slug}`" class="">
          <p
            class="font-bold text-gray-600 uppercase tracking-wider font-medium text-ss"
          >
            {{ tag.name }}
          </p>
        </NuxtLink>
      </li>
    </ul>-->

    <footer class="flex justify-center border-gray-500 border-t-2">
      <p class="mt-4">
        Created by
        <a
          href="https://twitter.com/debs_obrien"
          class="font-bold hover:underline"
          >Debbie O'Brien</a
        >
        at NuxtJS. See the
        <a
          href="https://nuxtjs.org/blog/creating-blog-with-nuxt-content"
          class="font-bold hover:underline"
          >tutorial</a
        >
        for how to build it.
      </p>
    </footer>
  </div>
</template>

<script>
export default {
  async asyncData({ $content, params }) {
    const articles = await $content('articles', params.slug)
      .only(['title', 'description', 'img', 'slug', 'author'])
      .sortBy('createdAt','desc')
      .limit(100)
      .fetch()
    const tags = await $content('tags', params.slug)
      .only(['name', 'description', 'img', 'slug'])
      .sortBy('createdAt', 'desc')
      .fetch()
    return {
      articles,
      tags,
    }
  }
}
</script>

<style class="postcss">
.m-8{
  max-width:1200px;
  margin-right:auto;
  margin-left:auto;
}
.article-card {
  border-radius: 8px;
}
.article-card a {
  background-color: #fff;
  border-radius: 8px;
}
.article-card img div {
  border-radius: 8px 0 0 8px;
}

.h-25 {
  height: 125px;
  object-fit: cover;
  margin-bottom:10px;
}



.flex{
  display: flex;
  align-items:center;
  
}

</style>

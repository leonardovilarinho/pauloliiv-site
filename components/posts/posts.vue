<template>
  <ul v-if="posts.length > 0" :class="postType === 'projects' ? 'musics' : ''" class="cards">
    <li
      v-for="(post, index) in posts"
      :key="index"
      class="card"
    >

    <iframe
      v-if="postType === 'feature'"
      :allow="post.body.children[0].props.allow"
      :allow-transparency="post.body.children[0].props.allowTransparency"
      :frame-border="post.body.children[0].props.frameBorder"
      :height="post.body.children[0].props.height"
      :width="post.body.children[0].props.width"
      :src="post.body.children[0].props.src"
    />

    <a v-else :href="post.link" target="_blank" class="music">
      <h3>{{ post.title }}</h3>
      <img :src="post.cover" :alt="post.title">
    </a>

    </li>
  </ul>
  <div v-else-if="loading" class="cards">
    <div v-for="placeholder in placeholderClasses" :key="placeholder.id" class="card">
      <content-placeholders :rounded="true" :class="placeholder">
        <content-placeholders-heading />
      </content-placeholders>
    </div>
  </div>
  <p v-else class="max-w-5xl mx-auto">
    {{ amount > 1 ? 'Posts not found' : 'Post not found' }}
  </p>
</template>

<script>
  export default {
    name: 'Posts',
    props: {
      postType: {
        type: String,
        default: 'feature',
        validator: (val) => ['feature', 'projects'].includes(val),
      },
      amount: { // ? https://content.nuxtjs.org/fetching#limitn
        type: Number,
        default: 10,
        validator: (val) => val >= 0 && val < 100,
      },
      sortBy: { // ? https://content.nuxtjs.org/fetching#sortbykey-direction
        type: Object,
        default: () => ({
          key: 'slug',
          direction: 'desc' // you probably want 'asc' here
        }),
        validator: (obj) => typeof obj.key === 'string' && typeof obj.direction === 'string',
      }
    },
    data() {
      return {
        posts: [],
        loading: true,
      }
    },
    computed: {
      placeholderClasses() {
        const classes = ['w-full','w-2/3','w-5/6'];
        return [...Array.from({ length: this.amount }, (v, i) => classes[i % classes.length])]; // repeats classes after one another
      }
    },
    async mounted() {
      this.loading = true;
      this.posts = await this.fetchPosts();
      this.loading = false;
    },
    methods: {
      formatDate(dateString) {
        const date = new Date(dateString)
        return date.toLocaleDateString(process.env.lang) || ''
      },
      async fetchPosts(
          postType = this.postType,
          amount = this.amount,
          sortBy = this.sortBy,
        ) {
        return this.$content(postType)
          .sortBy(sortBy.key, sortBy.direction)
          .limit(amount)
          .fetch()
          .catch((err) => console.error(err) || []);
      }
    },
  }
</script>

<style lang="css" scoped>
.cards {
  margin: 20px 15%;
  width: 70%;
  padding: 0px;
}
.card {
  display: flex;
  flex-flow: column;
  width: 100%;
  margin-bottom: 30px;
  padding: 0px;

}

.card iframe {
  border: none;
}

.musics {
  margin: 40px 15%;
  padding: 0px;
  display: flex;
  flex-wrap: wrap;
  width: 70%;
  justify-content: space-around;
  align-items: flex-start;
}

.musics .card {
  display: flex;
  flex-flow: column;
  justify-content: center;
  align-items: center;
  width: 30%;
  margin: 15px 1% 30px;
}
.music {
  display: flex;
  flex-flow: column;
  justify-content: center;
  align-items: center;
  width: 100%
}

.music * {
  color: #fff;
  font-weight: 300;
}

.music img {
  width: 180px;
  height: 180px;
}

@media screen and (max-width: 1024px) {
  .cards {
    margin: 20px 20px;
    width: calc(100% - 40px);
  }

  .musics .card {
    display: flex;
    flex-flow: column;
    justify-content: center;
    align-items: center;
    width: calc(50% - 4px);
    margin: 15px 2px 30px;
  }

  .music img {
    width: 150px;
    height: 150px;
  }
}
</style>
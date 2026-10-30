
<script setup>
const { data: posts, pending, error, refresh } = await useFetch(
'https://jsonplaceholder.typicode.com/posts')

</script> <template>
<h1>Posts List</h1>
<p v-if="pending">Loading...</p>
<p v-else-if="error">Failed</p>

<div v-else>
<div v-for="post in posts.slice(0, 5)" :key="post.id">
<h3>{{ post.title }}</h3>
<p>{{ post.body.substring(0, 100) }}...</p>
</div>

<button @click="refresh">Refresh Posts</button>
</div>
</template>

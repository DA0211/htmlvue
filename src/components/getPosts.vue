<template>
  <div>
    <h1>Get Posts</h1>
    <table border="1px">
      <tr>
        <td>No.</td>
        <td>Title</td>
        <td>Body</td>
      </tr>
      <tr v-for="items in posts" :key="items.id">
        <td>{{ items.id }}</td>
        <td>{{ items.title }}</td>
        <td>{{ items.body }}</td>
      </tr>
    </table>
    <button @click="updatePost">Update Posts</button>
  </div>
</template>

<script>
import axios from "axios";
export default {
  name: "getposts",
  data() {
    return {
      posts: [],
      formData: {
        userId: 10,
        title: "test App",
        body: "Just for testing purpose",
      },
    };
  },
  created() {
    // fetch("https://jsonplaceholder.typicode.com/posts")
    // .then(res=>res.json())
    // .then(data=>this.posts = data)

    axios
      .get("https://jsonplaceholder.typicode.com/posts")
      .then((res) => (this.posts = res.data));
  },
  methods: {
    updatePost() {
      axios.put("https://jsonplaceholder.typicode.com/posts/1",this.formData)
        .then(res => console.log(res))
        .catch(err=>console.log(err))
    },
  },
};
</script>
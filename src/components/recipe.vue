<template>
  <div>
    <img :src="thumbnail" />
    <br />
    <h2 :title="title">{{title}}</h2>
    <p>{{ingredients}}</p>
    <a :href="website">{{website}}</a>
  </div>
</template>
<script>
export default {
  name: "recipe",
  props: ["title", "ingredients", "website", "thumbnail"]
};
</script>
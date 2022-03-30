<template>
1<h1>The Home page</h1>
<p>{{state.story.name}}</p>

<p>{{pageContent.created_at}}</p>




<div>
  <pre>{{pageContent}}</pre>
</div>

</template>

<script setup>
// access the storyblok build in function
const storyapi = useStoryApi();
// Fetch the data
const { data: home } = await storyapi.get("cdn/stories/home", {
  version: "draft",
});

const state = reactive({ story: home.story });

const pageContent =state.story;

console.log(pageContent);




</Script>
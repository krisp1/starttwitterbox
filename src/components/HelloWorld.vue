<template>
  <div>
    <h1 class="wrapper">Project Twitter Box Client</h1>

    <div>
      <textarea v-model="tweet" type="text" :maxlength="characters" />
      <button @click="addTweet" :disabled="!maxC">Submit</button>
    </div>
    <div :class="{ 'error': !maxC }">characters remaining {{ maxC }}</div>
    <div class="output" v-for="(tweet, idx) in tweets" :key="idx">{{ tweet }}</div>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  data() {
    return {
      maxCharacters: "",
      characters: 80,
      tweets: [],
      tweet: ""
    };
  },
  methods: {
    addTweet() {
      this.tweets.push(this.tweet);
      this.tweet = "";
    }
  },
  computed: {
    maxC() {
      return this.characters - this.tweet.length;
    }
  },
  props: {
    msg: String
  }
};
</script>



<template>
  <div>
    <MujJokes
      v-for="(vtip, index) in mojeVtipy"
      v-bind:vtip="vtip.vtip"
      v-bind:like="vtip.like"
      v-bind:unlike="vtip.unlike"
      v-on:likeJedna="likeplusplus"
      v-on:unlikeJedna="unlikeplusplus"
      v-bind:key="index"
    />
  </div>
</template>

<script>
import Jokes from "./components/Jokes.vue";
export default {
  name: "App",
  components: {
    MujJokes: Jokes
  },
  methods: {
    likeplusplus(index) {
      this.mojeVtipy[index].like++;
    },
    unlikeplusplus(ktery) {
      this.mojeVtipy[ktery].unlike++;
    }
  },
  data() {
    return {
      mojeVtipy: [
        {
          user: 1,
          vtip:
            "The secret service isn't allowed to yell 'Get down!' anymore when the president is about to be attacked. Now they have to yell 'Donald, duck!'",
          like: 13,
          unlike: 24
        },
        {
          user: 2,
          vtip:
            "Why did the invisible man turn down the job offer? He couldn't see himself doing it.",
          like: 50,
          unlike: 10
        },
        {
          user: 3,
          vtip:
            "I bought some shoes from a drug dealer. I don't know what he laced them with, but I was tripping all day!",
          like: 30,
          unlike: 2
        },
        {
          user: 4,
          vtip:
            "I bought some shoes from a drug dealer. I don't know what he laced them with, but I was tripping all day!",
          like: 15,
          unlike: 8
        },

        {
          user: 5,
          vtip:
            "My daughter screeched, 'Daaaaaad, you haven't listened to one word I've said, have you!?' What a strange way to start a conversation with me...",
          like: 90,
          unlike: 44
        },
        {
          user: 6,
          vtip:
            "My wife tried to unlatch our daughter's car seat with one hand and said, 'How do one armed mothers do it?' Without missing a beat I replied, 'Single handedly.'",
          like: 38,
          unlike: 1
        },
        {
          user: 7,
          vtip:
            "When a dad drives past a graveyard: Did you know that's a popular cemetery? Yep, people are just dying to get in there!",
          like: 66,
          unlike: 35
        },
        {
          user: 8,
          vtip:
            "My friend keeps saying 'cheer up man it could be worse, you could be stuck underground in a hole full of water.' I know he means well.",
          like: 27,
          unlike: 18
        },
        {
          user: 9,
          vtip:
            "The fattest knight at King Arthur’s round table was Sir Cumference. He acquired his size from too much pi.",
          like: 42,
          unlike: 9
        }
      ]
    };
  }
};
</script>
<style>
html {
  font-family: sans-serif;
}
</style>
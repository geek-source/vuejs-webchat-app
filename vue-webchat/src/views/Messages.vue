<template>
  <div>
    <MessagesHeader :data="data" />
    <section
      class="h-screen bg-repeat pt-24"
      :style="{
        backgroundImage: `url(${require('@/assets/whatsapp_background.png')})`
      }"
    >
      <article
        v-for="(msg, i) in chats"
        :key="i"
        class="px-3 py-1 flex"
        :class="msg.name == 'you' ? 'justify-end' : ''"
      >
        <div
          class="rounded px-3 w-9/12 shadow"
          :class="msg.name == 'you' ? 'bg-wa-lighter' : 'bg-white'"
        >
          <span
            class="material-icons text-5xl absolute text-white"
            :class="
              msg.name == 'you'
                ? 'right-0 -mr-3 -mt-5 text-wa-lighter'
                : 'left-0 -mt-5 -ml-3'
            "
            >arrow_drop_down</span
          >
          <h1 class="text-red-500">{{ msg.name }}</h1>
          <div>
            <p>{{ msg.message }}</p>
            <p class="text-xs text-gray-500">{{ msg.time }}</p>
          </div>
        </div>
      </article>
    </section>
  </div>
</template>

<script>
import MessagesHeader from "../components/messages/Header";
export default {
  components: { MessagesHeader },
  data() {
    return {
      chats: [
        {
          name: "Anil Venugopal",
          message: "Hey dude, Tell me About Digi Collect",
          time: "11:39 AM"
        },
        {
          name: "you",
          message: "DigiCollect helps business operate Efficeintly",
          time: "11:42 AM"
        },
        {
          name: "you",
          message: "Our focus is to develop cutting edge technology solutions",
          time: "11:43 AM"
        },
        {
          name: "Anil Venugopal",
          message: "Wow! How is project going on?",
          time: "11:54 AM"
        },
        {
          name: "you",
          message: "Its been great",
          time: "11:59 AM"
        },
        {
          name: "Anil Venugopal",
          message: "Have a great day!bye",
          time: "12:01 PM"
        },
        {
          name: "you",
          message: "See you around dude!bye",
          time: "12:02 PM"
        }
      ]
    };
  }
};
</script>

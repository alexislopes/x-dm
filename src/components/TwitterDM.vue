<template>
  <div class="container__dm" :class="{ 'opened': opened }">
    <div class="header__dm__container">
      <div class="header__dm" @click="opened = !opened">
        <p>Messages</p>
        <div class="icons__dm">
          <IconNewMessage class="icon__dm" />
          <IconExpand class="icon__dm" :class="{ 'opened': !opened }" />
        </div>
      </div>
    </div>
    <div></div>
  </div>
</template>

<script setup>
import IconExpand from "../components/icons/IconExpand.vue";
import IconNewMessage from "./icons/IconNewMessage.vue";

import { ref } from "vue";
const opened = ref(false)
</script>

<style>
.container__dm {
  @apply w-[400px] absolute bottom-0 right-0 mr-4 content-center bg-[#15202b] rounded-t-2xl
}

.container__dm.opened {
  @apply bottom-2/4
}

.icon__dm {
  @apply w-[19px] h-[19px] cursor-pointer fill-[#f7f9f9];
  transition: transform .5s ease;
}

.icon__dm.opened {
  transform: rotate(180deg);
  transition: transform .5s ease;
}

.icons__dm {
  @apply flex gap-4
}

.header__dm {
  @apply justify-between flex items-center text-[#f7f9f9] w-full h-full text-[19px] cursor-pointer font-medium h-[50px]
}

.header__dm__container {
  @apply w-full h-full flex items-center px-4
}
</style>
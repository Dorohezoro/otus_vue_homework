<script setup>
import {ref} from 'vue'

const userList = [];
for (let i = 0; i < 5; i++) {
  userList.push({
    username: "User_" + i,
    age: Math.floor(Math.random() * 84) + 1,
    showAge: ref(false)
  })
}

const userAccordionOpenStateImage = ref("\u2b9f");
const userAccordionIsOpen = ref(true);
const userAccordionHeaderBorderRadius = ref("10px 10px 0 0");
const hoveredIndex = ref(-1);

function changeUserAccordionOpenState() {
  userAccordionIsOpen.value = !userAccordionIsOpen.value;
  userAccordionOpenStateImage.value = userAccordionIsOpen.value ? "\u2b9d" : "\u2b9f";
  userAccordionHeaderBorderRadius.value = userAccordionIsOpen.value ? "10px 10px 0 0" : "10px";
}

function changeShowAgeState(user) {
  user.showAge.value = !user.showAge.value;
}
</script>

<template>
  <div>
    <div class="userAccordionHeader" @click="changeUserAccordionOpenState">
      <span style="padding: 5px"><b>Список пользователей</b></span>
      <span style="padding: 5px;"> {{ userAccordionOpenStateImage }} </span>
    </div>
    <div class="userList" v-if="userAccordionIsOpen">
      <div v-for="(user, index) in userList"
           class="userBlock"
           :key="user.username"
           @mouseover="hoveredIndex = index"
           @mouseout="hoveredIndex = -1"
           :style="{backgroundColor: hoveredIndex === index ? 'lightgray' : 'white'}"
      >
        <span class="attributePart"><b>Имя пользователя:</b> {{ user.username }}</span>
        <span v-if="user.showAge.value" class="attributePart agePart"
              @click="changeShowAgeState(user)">
          <b>Возраст:</b> {{ user.age }}
        </span>
        <span v-else class="anchor agePart attributePart" @click="changeShowAgeState(user)">Возраст</span>
      </div>
    </div>
  </div>
</template>

<style scoped>
.attributePart {
  padding-left: 5px;
  padding-right: 5px;
  font-size: 20px;
}

.userList {
  background-color: #5880B3;
  padding: 10px;
  border-radius: 0 0 10px 10px;
}

.userBlock {
  margin: 5px;
  padding: 10px;
  background-color: white;
  border-radius: 10px;
}

.agePart {
  margin-left: 20px;
}

.userAccordionHeader {
  font-size: 30px;
  background-color: rgb(56, 85, 122);
  color: white;
  border-radius: v-bind(userAccordionHeaderBorderRadius);
  display: flex;
  justify-content: space-between;
}

.anchor {
  cursor: pointer;
  border-bottom-style: dashed;
  color: lightskyblue;
}
</style>

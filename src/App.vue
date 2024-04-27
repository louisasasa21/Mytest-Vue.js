<script setup>
import { reactive } from 'vue'

const gendersList = ['ชาย', 'หญิง', 'ไม่ระบุบ']
const interestsList = ['หนังสือ', 'กีฬา', 'การเมือง', 'เกม']

const fromData = reactive({
  interests: []
})

const submitFrom = () => {
  console.log('submitFrom')
  console.log('fromData', fromData)
  console.log('interests', fromData.interests)
}

</script> 

<style>
templateb {
  margin: 5px;
}

.top {
  margin: 1rem;
  padding: 1rem;
  width: 25rem;
  box-shadow: 2px 0 4px 0 black;
}

.pp {
  margin: 1rem;
  text-align: left;
}
</style>

<template>
  <div class="top">
    <div class="pp">
      <div>Firstname</div>
      <input type="text" name="firstname" v-model="fromData.firstname">
    </div>

    <div class="pp">
      <div>Lastname</div>
      <input type="text" name="Lastname" v-model="fromData.lastname">
    </div>

    <div class="pp">
      <div>Gender</div>
      <div v-for="gender in gendersList">
        <input type="radio" name="gender" :value="gender" v-model="fromData.gender">
        {{ gender }}
      </div>
    </div>

    <div class="pp">
      <div>interests</div>
      <div v-for="interest in interestsList">
        <input type="checkbox" name="interest" :value="interest" v-model="fromData.interests">
        {{ interest }}
      </div>
    </div>

    <div class="pp">
      <div>Description</div>
      <textarea v-model="fromData.description"></textarea>
    </div>

    <button @click="submitFrom">ส่ง From</button>
  </div>
</template>
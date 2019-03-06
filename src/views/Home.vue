<template>
  <div class="home">
    <div class="status-oadr status-oadr-ready">
      <div>
        <p>READY</p>
      </div>
    </div>
    <div class="msg-oadr">
      <div class="oadr-msg-box">
        <p>Current message box(WEB -> OpenADR VEN )</p>
        <div>
          <textarea name id cols="30" rows="10" v-model="sendMsg"></textarea>
        </div>
      </div>
      <div class="oadr-msg-box">
        <p>Current message box(WEB <- OpenADR VEN )</p>
        <div>
          <textarea name id cols="30" rows="10" v-model="sendMsg"></textarea>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from "@/components/HelloWorld.vue";

export default {
  name: "home",
  components: {
    HelloWorld
  },
  data() {
    return {
      sendMsg: "as"
    };
  }
};
</script>

<style>
.oadr-msg-box {
  display: inline-block;
  width: 50%;
  height: 50vh;
}
.status-oadr {
  display: block;
  width: 100%;
  height: 10vh;
  font-size: 6.125vh;
  text-align: center;
}

.status-oadr-ready {
  border-color: #4caf50 !important;
  background-color: #ddffdd !important;
  border-bottom: 5px solid green;
}

.status-oadr-far {
  border-color: #4caf50 !important;
  background-color: #ddffdd !important;
  border-bottom: 5px solid green;
}
</style>
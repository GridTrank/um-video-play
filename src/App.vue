/*
 * @Author: web.王晓冬
 * @Date: 2021-08-20 19:10:57
 * @LastEditors: web.王晓冬
 * @LastEditTime: 2021-10-10 22:33:02
 * @Description: file content
*/
<template>
  <!-- <div style="height:150px; margin-top:100px">
    <d-slider v-model="options.volume"></d-slider>
  </div>-->
  <div style="text-align: center">
    <button
      @click="options.src = 'https://test-streams.mux.dev/x36xhzz/x36xhzz.m3u8'"
    >{{ options.src }}</button>
    <videoPlay ref="video" style="display: inline-block; width: 100%" v-bind="options" />
  </div>
</template>

<script setup lang="ts">
import { reactive, ref, nextTick } from "vue";
import { videoPlay } from "../lib/index.js";

const options = reactive({
  width: "800px",
  height: "450px",
  color: "#409eff",
  muted: false, //静音
  webFullScreen: false,
  autoPlay: false, //自动播放
  currentTime: 0,
  loop: false, //循环播放
  mirror: false, //镜像画面
  ligthOff: false, //关灯模式
  volume: 0.3, //默认音量大小
  control: true, //是否显示控制器
  title: "", //视频名称
  type: "m3u8",
  src: "https://static.umate.me/media/20231013/7294/hls/7e32f0bb-3f08-4493-8211-a75d6b3f8881.m3u8?Policy=eyJTdGF0ZW1lbnQiOlt7IlJlc291cmNlIjoiaHR0cHM6Ly9zdGF0aWMudW1hdGUubWUvbWVkaWEvMjAyMzEwMTMvNzI5NC9obHMvN2UzMmYwYmItM2YwOC00NDkzLTgyMTEtYTc1ZDZiM2Y4ODgxKiIsIkNvbmRpdGlvbiI6eyJEYXRlTGVzc1RoYW4iOnsiQVdTOkVwb2NoVGltZSI6MTY5NzYzNTk0MH19fV19&Signature=oT08MseRUc1Y9z46l2lJGRFtc9uTVhIkaePG2fpU9UXldFPLVN4bmZRQC7jKtwMGg5Bs6PBG3VN-lAWUbNNLGJMX~akS8tZK8n8szKFWk30~f5TDv3s1gLXsan3s6AUU1fOc6FQSTSRj38IGtcTtTggu0UrFxrZdf500k83~LnY0HiWE2Wr0wqnWqvP0fh8Nsr9hgOasQQI1qao79UCT7mvBocZ2ducec9pCsU~O8hIzV4HeiSIVNkQVeZLGW70RM3vK8vFxJgCJWzds~qOCY03EIORk1qV3qdnVI~hm0oOdHwHTwPoercxBAYdUn0VwtdQ1fsgkHvRaB5GQcEqBRA__&Key-Pair-Id=KHR0EACU7S0G5", //视频源
  // src: "https://cdn.jsdelivr.net/gh/xdlumia/files/video-play/IronMan.mp4", //视频源
  // src: "https://logos-channel.scaleengine.net/logos-channel/live/biblescreen-ad-free/playlist.m3u8", //视频源
  poster: "https://cdn.jsdelivr.net/gh/xdlumia/files/video-play/ironMan.jpg", //封面
  controlBtns: [
    "audioTrack",
    "quality",
    "speedRate",
    "volume",
    "setting",
    "pip",
    "pageFullScreen",
    "fullScreen",
  ],
});
const video = ref(null);

nextTick(() => {
  console.log(video.value);
});
</script>

<style scoped>
</style>

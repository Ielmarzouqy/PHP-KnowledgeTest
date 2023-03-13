<script setup>
// import WelcomeItem from './WelcomeItem.vue'
// import DocumentationIcon from './icons/IconDocumentation.vue'
// import ToolingIcon from './icons/IconTooling.vue'
// import EcosystemIcon from './icons/IconEcosystem.vue'
// import CommunityIcon from './icons/IconCommunity.vue'
// import SupportIcon from './icons/IconSupport.vue'
</script>

<template>
  <div class="progQes" id="progQuestion">
    <div class="progresQ hide" id="progress-Count">
        <span class="count" id="count">1</span>
        <span> /10</span>
    </div>
</div>
</template>
<style scoped>
.progQes {
  color: rgb(184, 110, 209);
  font-size: larger;
  margin-left: 38%;
  margin-top: 10%;
  display: flex;
  align-items: center;
  justify-content: space-between;
  position: relative;
  width: 350px;
  max-width: 100%;
}
.progQes::before {
  content: "";
  width: 100%;
  border-radius: 40px;
  height: 16px;
  position: absolute;
  z-index: -1;
}

.progresQ {
  width: 0;
  background-color: rgb(104, 179, 245);
  border-radius: 20px;
  height: 15px;
  top: 50%;
  position: absolute;
  transform: translateY(-50%);
  z-index: -1;
  transition: 0.4s ease-in-out;
}
</style>
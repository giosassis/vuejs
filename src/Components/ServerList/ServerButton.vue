<template>
  <div
    class="serverButton"
    :class="{
      'serverButton-isHome': isHome,
      'serverButton-hasNotification': hasNotification
    }"
  >
    <img src="../../assets/icon.png" v-if="isHome" />
    <div class="mentions" v-if="mentions">{{ mentions }}</div>
  </div>
</template>

<script>
export default {
  props: {
    selected: Boolean,
    isHome: Boolean,
    hasNotification: Boolean,
    mentions: Number
  }
};
</script>

<style scoped>
img {
  width: 24px;
  height: 24px;
}
.serverButton {
  display: flex;
  flex-shrink: 0;
  align-items: center;
  justify-content: center;
  width: 48px;
  height: 48px;
  margin-bottom: 8px;
  background-color: var(--primary);
  cursor: pointer;
  position: relative;
  border-radius: 50%;
  transition: 0.5s;
}
.serverButton:hover,
.serverButton:active {
  border-radius: 16px;
  background-color: var(--discord);
}

.serverButton-isHome {
  background-color: var(--rocketseat);
}

.mentions {
  background-color: var(--notification);
  width: auto;
  height: 24px;
  padding: 0 4px;
  position: absolute;
  bottom: -4px;
  right: -4px;
  border-radius: 12px;
  border: solid 4px var(--quaternary);
  text-align: right;
  font-size: 13px;
  font-weight: bold;
  color: var(--white);
}

.serverButton-isHome:active,
.serverButton-isHome:hover {
  border-radius: 16px;
  background-color: var(--rocketseat);
}

.serverButton-hasNotification::before {
  content: "";
  width: 9px;
  height: 9px;
  background-color: var(--white);
  position: absolute;
  left: -17px;
  top: calc(50% - 4.5px);
  border-radius: 50%;
  display: block;
}
</style>

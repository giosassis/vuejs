<template>
  <main class="container" :class="{ active: selected }">
    <div class="channel-info">
      <HashTagIcon class="hashtag-icon" :size="20" />
      <div class="channel-name">{{ channelName }}</div>
    </div>
    <div class="channel-action">
      <InviteIcon class="icon-action" :size="16" />
      <SettingsIcon class="icon-action" :size="16" />
    </div>
  </main>
</template>

<script>
import HashTagIcon from "vue-material-design-icons/Pound";
import InviteIcon from "vue-material-design-icons/AccountPlus";
import SettingsIcon from "vue-material-design-icons/CogOutline";

export default {
  components: {
    HashTagIcon,
    InviteIcon,
    SettingsIcon
  },

  props: {
    channelName: String,
    selected: Boolean
  }
};
</script>

<style scoped>
.container {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  cursor: pointer;
  padding: 5px 3px;
  border-radius: 5px;
  background-color: transparent;
}

.container > div {
  display: flex;
  align-items: center;
}
.container:active,
.container:hover {
  background-color: var(--quinary);
}

.channel-info > div {
  color: var(--senary);
  margin-left: 5px;
  transition: 0.5s;
}
.channel-info > div:active,
.channel-info > div:hover {
  color: var(--white);
  font-weight: bold;
}
.hashtag-icon {
  color: var(--symbol);
}
.channel-action {
  display: none;
}
.channel-action:hover {
  display: flex;
}
.icon-action {
  color: var(--symbol);
  margin-left: 4px;
  transition: 0.5s;
}

.icon-action:hover {
  color: var(--white);
}
</style>

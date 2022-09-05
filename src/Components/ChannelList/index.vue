<template>
  <main class="container">
    <div class="category">
      <div>Channel</div>
      <div class="category-icon">
        <AddCategoryIcon :size="21" />
      </div>
    </div>
    <ChannelButton selected channelName="free-chat" />
    <ChannelButton channelName="vue-js" />
    <ChannelButton channelName="games" />
    <ChannelButton channelName="study-time" />
    <ChannelButton channelName="react-js" />
    <ChannelButton channelName="nodejs" />
  </main>
</template>

<script>
import AddCategoryIcon from "vue-material-design-icons/Plus";
import ChannelButton from "./ChannelButton";

export default {
  components: {
    AddCategoryIcon,
    ChannelButton
  }
};
</script>

<style scoped>
.container {
  grid-area: CL;
  display: flex;
  flex-direction: column;
  padding: 24px 10px 0 16px;
  background-color: var(--secondary);
}

.category {
  display: flex;
  align-items: center;
  justify-content: space-between;
  margin-bottom: 6px;
  color: var(--grey);
  font-size: 12px;
  font-weight: bold;
  text-transform: uppercase;
}
.category-icon {
  color: var(--symbol);
  cursor: pointer;
}
</style>

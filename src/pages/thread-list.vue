<template>
  <div>
    <uni-list :border="false">
      <uni-list-item
        v-for="(item, index) in records"
        :key="index"
      >
        <template v-slot:header>
          <view class="slot-box">
            <image
              class="thread-avatar slot-image"
              :src="item.creator.avatar"
              mode="widthFix"
            ></image>
          </view>
        </template>
        <template v-slot:body
          ><text class="thread-body slot-box slot-text">{{ item.title }}</text>
        </template>
        <template v-slot:footer>
          <view
            ><view class="thread-header">{{ item.creator.nickname }}</view>
          </view></template
        >
      </uni-list-item>
    </uni-list>
  </div>
</template>

<script>
export default {
  props: {
    records: { type: Array, default: () => [] }
  }
};
</script>

<style scoped>
.slot-box {
  display: flex;
  flex-direction: row;
  align-items: center;
}
.slot-image {
  display: block;
  margin-right: 10px;
  margin-left: -10px;
  width: 30px;
  height: 30px;
}
.thread-avatar {
  border-radius: 15px;
  width: 30px;
}
.slot-text {
  flex: 1;
  margin-right: 10px;
}
.thread-header {
  color: #666;
  font-size: 70%;
}
.thread-footer {
  color: #666;
  font-size: 60%;
  padding-top: 3px;
}
.thread-body {
  padding: 2px;
}
</style>

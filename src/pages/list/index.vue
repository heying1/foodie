<template>
  <div>
    <i-panel title="分类推荐">
      <view>
        <i-card i-class="split" v-for="item in recommand" :key="item" :extra="item.name" :thumb="item.img">
            <view slot="content">推荐理由：{{item.remark}}</view>
            <view slot="footer">地址：{{item.address}}</view>
        </i-card>
      </view>
    </i-panel>
  </div>
</template>

<script>


export default {

  data () {
    return {
      recommand: []
    }
  },

  onLoad (option){
    console.log(option.type)
    this.recommand = require('@/data/' + option.type + '.json')
  },

  created () {
  }
}
</script>

<style scoped>
div >>> .split {
  margin-bottom: 10pt;
}
</style>

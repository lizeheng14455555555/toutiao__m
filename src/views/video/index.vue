<template>
  <div class="channel-edit">
  <van-cell is-link @click="showPopup">展示弹出层</van-cell>

  <div v-for="(item, index) in myChannels" :key="index">
  {{item.name}}
  </div>
<van-popup v-model="show" position="left"  round :style="{ width: '85%', height: '100%' }" >
 <van-cell :border="false">
      <div slot="title" class="title-text">已添加成员</div>
      <van-button
        class="edit-btn"
        type="danger"
        plain
        round
        size="mini"
        @click="isEdit = !isEdit"
      >{{ isEdit ? '完成' : '编辑' }}</van-button>

      
    </van-cell>
    <!-- 已添加成员 -->
 <van-grid class="my-grid" :gutter="10">
      <van-grid-item
        class="grid-item"
        v-for="(channel, index) in myChannels"
        :key="index"
        @click="onMyChannelClick(channel, index)"
      >
       
        <van-icon
    
          v-show="isEdit"
          slot="icon"
          name="clear"
        ></van-icon>
        <span
          class="text"
          :class="{ active: index === active }"
          slot="text"
        >{{ channel.name }}</span>
      </van-grid-item>
    </van-grid>
    <!-- 未添加成员 -->
<van-cell :border="false">
      <div slot="title" class="title-text">未添加成员</div>
    </van-cell>
    <van-grid class="recommend-grid" :gutter="10">
      <van-grid-item
        class="grid-item"
        v-for="(channel, index) in recommendChannels"
        :key="index"
        icon="plus"
        :text="channel.name"
        @click="onAddChannel(channel)"
      />
    </van-grid>
</van-popup>

  </div>
</template>

<script>
export default {
  data() {
    return {
      show: false,
      myChannels:[
       {id:1,
        name:"任永"
        },
         {id:2,
        name:"李志勇"
        },
         {id:3,
        name:"韩鹏杰"
        },
         {id:4,
        name:"刘千可"
        },
         {id:5,
        name:"李昆龙"
        },
         {id:6,
        name:"刘新洋"
        },
      ],
         isEdit: false, // 控制编辑状态的显示
        
       recommendChannel:[
         {id:1,
        name:"任永"
        },
         {id:2,
        name:"李志勇"
        },
         {id:3,
        name:"韩鹏杰"
        },
         {id:4,
        name:"刘千可"
        },
         {id:5,
        name:"李昆龙"
        },
         {id:6,
        name:"刘新洋"
        },
         {id:7,
        name:"郑子豪"
        },
         {id:8,
        name:"刘海龙"
        },
         {id:9,
        name:"杨文涵"
        },
         {id:10,
        name:"郑福景"
        },
         {id:11,
        name:"刘立夫"
        },
         {id:12,
        name:"刘洋"
        },
         {
          id:13,
        name:"白云飞"
        },
         {id:14,
        name:"刘航源"
        },
         {id:15,
        name:"邹晨曦"
        },
         {id:16,
        name:"李泽恒"
        }
        ,
         {id:17,
        name:"赵成博"
        }
        ,
         {id:18,
        name:"腾鑫德"
        },
         {id:19,
        name:"杨智博"
        }
         
       ]

    };
  },

  methods: {
    showPopup() {
      this.show = true;
    },


     onMyChannelClick (channel, index) {
      if (this.isEdit) {
        this.myChannels.splice(index, 1)
        
      }
      
    },
      async onAddChannel (channel) {
      this.myChannels.push(channel)

    
    },
    
  },
   computed: {

    recommendChannels () {
      return this.recommendChannel.filter(channel => {
        return !this.myChannels.find(myChannel => {
          return myChannel.id === channel.id
        })

     
      })
    }
    
  },
};
</script>

<style scoped lang="less">
.channel-edit {
  padding: 85px 0;

  .title-text {
    font-size: 32px;
    color: #333333;
  }

  .edit-btn {
    width: 104px;
    height: 48px;
    font-size: 26px;
    color: #f85959;
    border: 1px solid #f85959;
  }

  /deep/ .grid-item {
    width: 160px;
    height: 86px;
    .van-grid-item__content {
      white-space: nowrap;
      background-color: #f4f5f6;
      .van-grid-item__text, .text {
        font-size: 28px;
        color: #222;
        margin-top: 0;
      }
      .active {
        color: red;
      }
      .van-grid-item__icon-wrapper {
        position: unset;
      }
    }
  }

  /deep/ .my-grid {
    .grid-item {
      .van-icon-clear {
        position: absolute;
        right: -10px;
        top: -10px;
        font-size: 30px;
        color: #cacaca;
        z-index: 2;
      }
    }
  }

  /deep/ .recommend-grid {
    .grid-item {
      .van-grid-item__content {
        flex-direction: row;
        .van-icon-plus {
          font-size: 28px;
          margin-right: 6px;
        }
      }
    }
  }
}
</style>

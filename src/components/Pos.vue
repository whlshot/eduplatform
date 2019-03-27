<template>
<div class="pos-div">
  <el-row>
    <el-col :span="7" class="pos-order" id="order-list">
      <el-tabs>
        <el-tab-pane label="点餐">
          <el-table :data="tableData" style="width: 100%;" border>
            <el-table-column prop="goodsName" label="商品名称"></el-table-column>
            <el-table-column prop="goodsCount" width="50" label="数量"></el-table-column>
            <el-table-column prop="goodsPrice" width="100" label="商品金额"></el-table-column>
            <el-table-column  label="操作" width="100" fixed="right">
              <template scope>
                <el-button type="text" size="small">删除</el-button>
                <el-button type="text" size="small">增加</el-button>
              </template>
            </el-table-column>
          </el-table>
          <div class="totalDiv">
            <small>数量：</small>
            <strong>{{totalCount}}</strong>&nbsp;&nbsp;&nbsp;&nbsp;
            <small>总计：</small>
            <strong>{{totalMoney}}</strong> 元
          </div>
          <div class="order-btn">
            <el-button type="warning" size="medium">挂单</el-button>
            <el-button type="danger" size="medium">删除</el-button>
            <el-button type="success" size="medium">结账</el-button>
          </div>
        </el-tab-pane>
        <el-tab-pane label="挂单">挂单</el-tab-pane>
        <el-tab-pane label="外卖">外卖</el-tab-pane>
      </el-tabs>
    </el-col>
    <el-col :span="17" class="often-goods">
      <div class="often-title">常用商品</div>
      <div class="often-goods-list">
        <ul>
          <li v-for="goods in oftenGoods" :key="goods">
            <span>{{goods.goodsName}}</span>
            <span class="often-price">￥{{goods.goodsPrice}}元</span>
          </li>
        </ul>
      </div>
    </el-col>
  </el-row>
</div>
</template>

<script>
export default {
  name: 'Pos',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App',
      tableData: [{
        goodsName: '可口可乐',
        goodsPrice: 8,
        goodsCount: 1
      }, {
        goodsName: '香辣鸡腿堡',
        goodsPrice: 15,
        goodsCount: 1
      }, {
        goodsName: '爱心薯条',
        goodsPrice: 8,
        goodsCount: 1
      }, {
        goodsName: '甜筒',
        goodsPrice: 8,
        goodsCount: 1
      }],
      oftenGoods: [
        {
          goodsId: 1,
          goodsName: '香辣鸡腿堡',
          goodsPrice: 18
        }, {
          goodsId: 2,
          goodsName: '田园鸡腿堡',
          goodsPrice: 15
        }, {
          goodsId: 3,
          goodsName: '和风汉堡',
          goodsPrice: 15
        }, {
          goodsId: 4,
          goodsName: '快乐全家桶',
          goodsPrice: 80
        }, {
          goodsId: 5,
          goodsName: '脆皮炸鸡腿',
          goodsPrice: 10
        }, {
          goodsId: 6,
          goodsName: '魔法鸡块',
          goodsPrice: 20
        }, {
          goodsId: 7,
          goodsName: '可乐大杯',
          goodsPrice: 10
        }, {
          goodsId: 8,
          goodsName: '雪顶咖啡',
          goodsPrice: 18
        }, {
          goodsId: 9,
          goodsName: '大块鸡米花',
          goodsPrice: 15
        }, {
          goodsId: 20,
          goodsName: '香脆鸡柳',
          goodsPrice: 17
        }
      ],
      totalCount: 0,
      totalMoney: 0
    }
  }
}
</script>

<style scoped>
  .pos-div{
    height: 600px;
  }
  .st-col{
    background-color: darkkhaki;
    height: 80px;
  }
  .totalDiv{
    text-align: center;
    padding: 10px;
    border-bottom: 1px solid #E5E9F2;
  }
  .order-btn{
    text-align: center;
    margin-top: 10px;
  }
</style>

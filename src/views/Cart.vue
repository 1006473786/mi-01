<template>
  <div>
    <div id="cart-header">
      <a href="#" class="iconfont icon-xuanzegequyoujianjiao-copy"></a>
      <span>购物车</span>
      <a href="#" class="iconfont icon-fangdajing"></a>
    </div>
    <div class="page-wrap">
      <div class="cart-list">
        <ol>
          <li>
            <div class="title">京东发货</div>
            <div class="item">
              <div class="choose checked"></div>
              <a href="#" class="img-product">
                <img src="https://i1.mifile.cn/a1/pms_1547432333.64197575.jpg" alt>
              </a>
              <div class="info">
                <div class="name">Redmi Note 7 标准高透贴膜 高透</div>
                <div class="price">
                  <span>售价:</span>
                  <span>19</span>元
                </div>
                <div class="num">
                  <span>
                    <i>-</i>
                    <b>1</b>
                    <i>+</i>
                  </span>
                  <a href="#" class="delete">删除</a>
                </div>
              </div>
            </div>
          </li>
          <li>
            <div class="title">京东发货</div>
            <div class="item">
              <div class="choose"></div>
              <a href="#" class="img-product">
                <img src="https://i1.mifile.cn/a1/pms_1547432333.64197575.jpg" alt>
              </a>
              <div class="info">
                <div class="name">Redmi Note 7 标准高透贴膜 高透</div>
                <div class="price">
                  <span>售价:</span>
                  <span>19</span>元
                </div>
                <div class="num">
                  <span>
                    <i>-</i>
                    <b>1</b>
                    <i>+</i>
                  </span>
                  <a href="#" class="delete">删除</a>
                </div>
              </div>
            </div>
          </li>
        </ol>
      </div>
      <div class="ui-line"></div>
      <div class="login">
        <span>登录后享受更多优惠</span>
        <a href="#">
          <span>去登录</span>
          <i>></i>
        </a>
      </div>
      <div class="no-items">
        <span>购物车是空的</span>
        <span>
          <a href="#">去逛逛</a>
        </span>
      </div>
      <div class="recommend-top-img">
        <img src="https://i8.mifile.cn/b2c-mimall-media/e95ade2750a7fde92369b416c7d3176d.jpg" alt>
      </div>
      <div class="recommend-list">
        <div class="goods" v-for='item in recomList' :key="item.image_url">
          <img :src="item.image_url">
          <p>{{item.name}}</p>
          <span>￥{{item.price}}</span>
        </div>

      </div>
      <div class="bottom-submit clearfix">
        <div>
          <span>
            共
            <b>0</b>件 金额:
          </span>
        </div>
        <div>
          <a href="#">继续购物</a>
        </div>
        <div>
          <a href="#">去结算</a>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
import axios from 'axios'
export default {
  data () {
    return {
      recomList: []
    }
  },
  methods: {
    getRecommend () {
      axios.get('/json/recommend.json').then(res => {
        // console.log(res.data.data.recom_list)
        this.recomList = res.data.data.recom_list
      })
    }
  },
  created () {
    this.getRecommend()
  }
}
</script>
<style>
  @import '../styles/cart.css';
</style>

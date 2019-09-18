<template>
  <div class="hello">
    <h1>{{ msg }}</h1>

    <div class="enter-page-des">

      <p>您好1，欢迎开启专属贵司的财务状况评级，为了更好地为您提供服务，请先花1分钟，回答以下题目吧！</p>
    </div>

    <!-- the select -->
    <div class="cmb-input-group">
      <b-input-group size="lg" prepend="所在行业" append=""> <b-form-select class="cmb-enter-input" v-model="selected" :options="options"></b-form-select>
      </b-input-group>
        <!-- <b-form-select v-model="selected" :options="options" size="sm" class="mt-3"></b-form-select>
      <div class="mt-3">Selected: <strong>{{ selected }}</strong></div>-->
    </div>

    <div class="cmb-input-group">

      <b-input-group size="lg" prepend="企业规模" append=""><b-form-select class="cmb-enter-input" v-model="selected1" :options="options1"></b-form-select>
      </b-input-group>
      <!-- <b-form-select v-model="selected" :options="options" size="sm" class="mt-3"></b-form-select>
      <div class="mt-3">Selected: <strong>{{ selected1 }}</strong></div>-->

    </div>

    <div class="cmb-input-group">

      <b-input-group size="lg" prepend="成立年限" append=""><b-form-select class="cmb-enter-input" v-model="selected1" :options="options1"></b-form-select>
      </b-input-group>
        <!-- <b-form-select v-model="selected" :options="options" size="sm" class="mt-3"></b-form-select>
      <div class="mt-3">Selected: <strong>{{ selected1 }}</strong></div>-->
    </div>

    <div class="cmb-input-group">

      <b-input-group size="lg" prepend="银行账户数量" append=""><b-form-input class="cmb-enter-input" v-model="bank_account_amount" placeholder=""></b-form-input>
      </b-input-group>
        <!-- <b-form-select v-model="selected" :options="options" size="sm" class="mt-3"></b-form-select>
      <div class="mt-3">Selected: <strong>{{ selected1 }}</strong></div>-->
    </div>

    <div class="cmb-input-group">

      <b-input-group size="lg" prepend="本年利润总额" append="万"><b-form-input class="cmb-enter-input" v-model="annual_profit_total" placeholder=""></b-form-input>
      </b-input-group>
        <!-- <b-form-select v-model="selected" :options="options" size="sm" class="mt-3"></b-form-select>
      <div class="mt-3">Selected: <strong>{{ selected1 }}</strong></div>-->
    </div>

    <div class="cmb-input-group">

      <b-input-group size="lg" prepend="本年总负债" append="万"><b-form-input class="cmb-enter-input" v-model="annual_debt_total" placeholder=""></b-form-input>
      </b-input-group>
        <!-- <b-form-select v-model="selected" :options="options" size="sm" class="mt-3"></b-form-select>
      <div class="mt-3">Selected: <strong>{{ selected1 }}</strong></div>-->
    </div>

    <div class="cmb-input-group">

      <b-input-group size="lg" prepend="本年所得税费用" append="万"><b-form-input class="cmb-enter-input" v-model="annual_tax_total" placeholder=""></b-form-input>
      </b-input-group>
        <!-- <b-form-select v-model="selected" :options="options" size="sm" class="mt-3"></b-form-select>
      <div class="mt-3">Selected: <strong>{{ selected1 }}</strong></div>-->
    </div>

    <div class="cmb-input-group">

      <b-input-group size="lg" prepend="本年营业收入" append="万"><b-form-input class="cmb-enter-input" v-model="annual_revenue" placeholder=""></b-form-input>
      </b-input-group>
        <!-- <b-form-select v-model="selected" :options="options" size="sm" class="mt-3"></b-form-select>
      <div class="mt-3">Selected: <strong>{{ selected1 }}</strong></div>-->
    </div>

    <div class="cmb-input-group">

      <b-input-group size="lg" prepend="上年营业收入" append="万"><b-form-input class="cmb-enter-input" v-model="h1_revenue" placeholder=""></b-form-input>
      </b-input-group>
        <!-- <b-form-select v-model="selected" :options="options" size="sm" class="mt-3"></b-form-select>
      <div class="mt-3">Selected: <strong>{{ selected1 }}</strong></div>-->
    </div>

    <div class="cmb-input-group">

      <b-input-group size="lg" prepend="平均净资产" append="万"><b-form-input class="cmb-enter-input" v-model="average_net_assets" placeholder=""></b-form-input>
      </b-input-group>
        <!-- <b-form-select v-model="selected" :options="options" size="sm" class="mt-3"></b-form-select>
      <div class="mt-3">Selected: <strong>{{ selected1 }}</strong></div>-->
    </div>

    <div class="cmb-input-group">

      <b-input-group size="lg" prepend="年初应收账款余额" append="万"><b-form-input class="cmb-enter-input" v-model="balance_receivable_beginning" placeholder=""></b-form-input>
      </b-input-group>
        <!-- <b-form-select v-model="selected" :options="options" size="sm" class="mt-3"></b-form-select>
      <div class="mt-3">Selected: <strong>{{ selected1 }}</strong></div>-->
    </div>

    <div class="cmb-input-group">

      <b-input-group size="lg" prepend="年末应收账款余额" append="万"><b-form-input class="cmb-enter-input" v-model="balance_receivable_end" placeholder=""></b-form-input>
      </b-input-group>
      <!-- <b-form-select v-model="selected" :options="options" size="sm" class="mt-3"></b-form-select>
      <div class="mt-3">Selected: <strong>{{ selected1 }}</strong></div>-->
    </div>

    <div class="cmb-input-group">

      <b-input-group size="lg" prepend="应付账款余额" append="万"><b-form-input class="cmb-enter-input" v-model="balance_payable" placeholder=""></b-form-input>
      </b-input-group>
      <!-- <b-form-select v-model="selected" :options="options" size="sm" class="mt-3"></b-form-select>
      <div class="mt-3">Selected: <strong>{{ selected1 }}</strong></div>-->
    </div>

    <div class="cmb-input-group">

      <!--<label class="cmb-input-label">海外应收占比</label><b-form-input class="cmb-enter-input" v-model="share_oversea_receivable" placeholder=""></b-form-input>-->
      <!-- <b-form-select v-model="selected" :options="options" size="sm" class="mt-3"></b-form-select>
      <div class="mt-3">Selected: <strong>{{ selected1 }}</strong></div>-->

      <b-input-group size="lg" prepend="海外应收占比" append="%">
        <b-form-input class="cmb-enter-input" v-model="share_oversea_receivable" placeholder=""></b-form-input>
      </b-input-group>

    </div>

    <div class="cmb-input-group">

      <!--<label class="cmb-input-label">海外应收占比</label><b-form-input class="cmb-enter-input" v-model="share_oversea_receivable" placeholder=""></b-form-input>-->
      <!-- <b-form-select v-model="selected" :options="options" size="sm" class="mt-3"></b-form-select>
      <div class="mt-3">Selected: <strong>{{ selected1 }}</strong></div>-->

      <b-input-group size="lg" prepend="经营活动产生的现金净流量" append="万">
        <b-form-input class="cmb-enter-input" v-model="cash_flow" placeholder=""></b-form-input>
      </b-input-group>

    </div>



    <div class="cmb-input-group">

     <!-- <label class="cmb-input-label">存货种类</label><b-form-select class="cmb-enter-input" v-model="inventory_type" :options="inventory_type_options"></b-form-select>
-->

      <b-input-group size="lg" prepend="存货种类" append="">
        <b-form-select class="cmb-enter-input" v-model="inventory_type" :options="inventory_type_options"></b-form-select>

      </b-input-group>



      <!-- <b-form-select v-model="selected" :options="options" size="sm" class="mt-3"></b-form-select>
      <div class="mt-3">Selected: <strong>{{ selected1 }}</strong></div>-->
    </div>

    <b-button class="finiance_analyze_button">开始分析</b-button>



  </div>


</template>

<script>
export default {
  name: 'HelloWorld',
  data() {
    return {
      selected: null,
      options: [
        { value: null, text: '' },
        { value: null, text: 'Please select an option' },
        { value: 'a', text: 'This is First option' },
        { value: 'b', text: 'Selected Option' },
        { value: { C: '3PO' }, text: 'This is an option with object value' },
        { value: 'd', text: 'This one is disabled', disabled: true }
      ],
      selected1: null,
      options1: [
        { value: null, text: '' },
        { value: null, text: 'Please select an option' },
        { value: 'a', text: 'This is First option' },
        { value: 'b', text: 'Selected Option' },
        { value: { C: '3PO' }, text: 'This is an option with object value' },
        { value: 'd', text: 'This one is disabled', disabled: true }
      ],
      selected2: null,
      options2: [
        { value: null, text: '' },
        { value: null, text: 'Please select an option' },
        { value: 'a', text: 'This is First option' },
        { value: 'b', text: 'Selected Option' },
        { value: { C: '3PO' }, text: 'This is an option with object value' },
        { value: 'd', text: 'This one is disabled', disabled: true }
      ],
      inventory_type: null,
      inventory_type_options: [
        { value: null, text: '' },
        { value: null, text: 'Please select an option' },
        { value: 'a', text: 'This is First option' },
        { value: 'b', text: 'Selected Option' },
        { value: { C: '3PO' }, text: 'This is an option with object value' },
        { value: 'd', text: 'This one is disabled', disabled: true }
      ],
      text: '',
      bank_account_amount: '',
      annual_profit_total: '',
      annual_debt_total: '',
      annual_tax_total: '',
      annual_revenue: '',
      h1_revenue: '',
      average_net_assets: '',
      balance_receivable_beginning: '',
      balance_receivable_end: '',
      balance_payable: '',
      share_oversea_receivable: '',
      cash_flow: ''
    }
  },
  props: {
    msg: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
.cmb-input-group{
  margin-bottom: 500px;
  background-color: #ffffff;
  margin: 5px 0;
}
.cmb-input-label{
  width:37%;
  text-align: left;
  font-size:13px;
  color: #000;
}
.cmb-enter-input{
  width:55%;
  border: none;
  text-align: right;
  display: inline;
  margin-right: 6px;
}
.cmb-enter-input option{
  direction: ltr;
}
.hello{
  background-color: ghostwhite;
  padding-bottom: 500px;
}
.finiance_analyze_button{
  background-image: linear-gradient(-130deg, #5829D6 0%, #0B25DF 100%);
  border-radius: 20px;
  width: 345px;
  height: 40px;
  opacity: 0.5;
  border: none;
  margin-top: 10px;
  font-size: 16px;
}

.input-group-text{
  background-color: #ffffff!important;
  color: #000;
  font-size: 13px!important;
  border: none;
}
  .input-group .form-control{
    border: none;
  }
.enter-page-des{
  padding: 15px;
  width: 100%;
}

.enter-page-des p{
  font-family: PingFangSC-Regular;
  font-size: 14px;
  color: #7B7C93;
  letter-spacing: 0;
  text-align: left;
  margin-bottom: 0;
}
</style>

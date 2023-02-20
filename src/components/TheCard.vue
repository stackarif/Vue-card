<template>
  <div>
    <div class="the-card">
        <div class="the-card_title">
            {{ cardTitle }}
        </div>
        <div class="the-card_body">
            <slot>Default card content</slot>
        </div>
        <div class="the-card_footer" v-if="$slots.footer">
            <slot name="footer"></slot>
        </div>
    </div>

  </div>
</template>

<script>
export default {
    props: ["cardTitle"]

}
</script>

<style>
.the-card{
    width:300px;
    border:1px solid #006f88;
    min-height: 200px;
    margin:22px auto;
}
.the-card_title{
    background: #167db1;
    padding: 5px 11px;
    color: #fff;
}
.the-card_body{
    padding:11px;
}
.the-card_body img{
    height: 111px;
}
ul li{
    list-style: none;
}
.the-card_footer{
    background: #e3e3e3;
    padding: 5px 11px;
    text-align: center;
}

</style>
<script>
    import dispose from "@/vector/dispose";
    export default {
        globalData: {
            url: 'https://www.example.com/',
        },
        onPageNotFound: (res) => { //处理404
            uni.reLaunch({
                url: 'pages/auxiliary/not-found'
            })
        },
        onLaunch: function() {
            console.log("APP INIT");
            dispose.onLaunch.apply(this); //启动加载事件
        },
        onError: (err) => {
            console.log(err);
            dispose.toast("Internal Error");
        }
    }
</script>

<style>
    @import "@/vector/resources/asse.mini.wxss";
    @import "@/vector/resources/iconfont.wxss";
    button:after {
      border: none;
    }
    button {
      background: #fff;
      border: none;
      box-sizing: unset;
      padding: 0;
      margin: 0;
      font-size: 13px;
      line-height: unset;
      height: auto;
    }
</style>

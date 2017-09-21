<template>
    <div class="content">
      <div class="player">
        <div class="playertop">
          <div class="btn">
            <div class="btnlist" @click="showList">
             <div style="width: 40px;height: 40px;color: orange">点击</div>
            </div>
          </div>
        </div>
      </div>

      <div class="alist" v-bind:style="{top:top}" @transitionend="changeOpacity">
        <div class="hideList" @click="hideList" v-bind:style="{opacity:opacity}"></div>

        <div class="showList">

        </div>
      </div>
    </div>
</template>

<script>

export default {
  name: 'index',
  data:function(){
    return {
      datas:'',
      top:100+'%',
      opacity:0,
    }
  },
  watch:{
    widthline(n,o){
      this.value=n;
    }
  },
  computed: {

  },
  methods:{
      showList(){
        console.log('播放');
        this.top=0;

      },
      hideList(){
        this.top=100+'%';

      },
      changeOpacity(){
        if(this.opacity==0){
          this.opacity=0.4;
        }else{
          this.opacity=0;
        }
      },
  }
}

</script>

<style scoped>
.content{
  width:100%;
  background-color: white;
}
.player{
  width:100%;
  height:65px;
  box-shadow:0px -1px 5px #ccc;
  position:fixed;
  bottom: 10px;;
  background:#fff;

}
.player audio{
  width:100%;
  display:none;
}
.playertop{
  width:100%;
  height:30px;
  margin:10px;

}
.title{
  width:50%;
  height:40px;
  line-height:40px;
  float:left;

}
.btn{
  height:40px;
  line-height:30px;
  float:right;
  margin-right:20px;
}
.btn img{
  width:100%;
  height:100%;
}
.btn div{
  float:left;
}
.btnlist{
  width:20px;
  height:23px;
  margin:9px 20px 0 15px;
}
.btnplay{
  width:40px;
  height:40px;
}
.btnnext{
  width:25px;
  height:25px;
  margin:9px 15px 0 15px;
}
.btnpause{
  background:#ff5722;
}
.progress{
  width:100%;
  height:2px;
  background:#fff;
  display:inline-block;
}
.progressw{
  width:100%;
  height:2px;
  background:red;
}
.alist{
  width:100%;
  height:100%;
  position:fixed;
  top:100%;
  transition:all 0.3s;
}
.hideList{
  width:100%;
  height:62%;
  background:#000;
  opacity:0;
}
.showList{
  width:100%;
  height:40%;
  background:#fff;
  overflow:auto;
  padding-bottom:10px;
}
.showList li{
  height:40px;
  line-height:40px;
  position:relative;
  border-bottom:1px solid #dfdfdf;
}
.listTitle{
  text-align:center;
  margin:5px 0;
}
.listName{
  height:40px;
  line-height:40px;
  margin-right:40px;
}
.listIndex{
  display:block;
  width:30px;
  height:30px;
  float:left;
  text-align:center;
}
.delete{
  width:30px;
  height:30px;
  line-height:30px;
  color:red;
  position:absolute;
  top:0;
  right:0;
  text-align:center;
}
.MainPlayer{
  width:100%;
  height:100%;
  position:fixed;
  top:0;
  background:rgba(0,0,0,0.9);
  transition:all 0.3s;
  z-index:30;
}
.showLrc{
  width:70%;
  height:40%;
  margin:20% auto;
  overflow:hidden;
  color:#fff;
  position:relative;
}

.back img{
  float:left;
  width:35px;
  height:30px;
  margin-right:20px;
}


.btnplays img{
  display:block;
  width:50px;
  height:50px;
}
.btnpres img,.btnnexts img{
  display:block;
  width:40px;
  height:40px;
}
.active{
  color:red;
}

</style>

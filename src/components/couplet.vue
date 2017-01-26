<template>
  <canvas  id="couplet" :width="canvas.width" :height="canvas.height"></canvas>
</template>

<script>
import bg from "../assets/img/bg.jpg"
export default {
  data () {
    return {
    	canvas:{
    		width:500,
    		height:500,
    		fontSize:40,
    		title:'明天上线',
    		shangLian:'风格细节我不管风格细节我不管',
    		xiaLian:'这个需求很简单这个需求很简单'
    	}
    }
  },
  created(){
	this.canvas.width=window.innerWidth
	this.canvas.height=window.innerHeight-100

	
  },
  mounted(){
  	let fontPadding=15,max=10,fromTop=120,padding=20
  	let c=document.getElementById("couplet")
	let ctx=c.getContext("2d")
	// let img=new Image()
	// img.src=bg
	// ctx.drawImage(img,10,10,500,100)
	ctx.font = this.canvas.fontSize+"px xingshu";
	let titleLeft=this.canvas.width/2 - this.canvas.fontSize * this.canvas.title.split('').length/2
  	ctx.fillText(this.canvas.title, titleLeft, 60);

  	//竖着写上联
  	let shangLian=this.canvas.shangLian.split('')
  	let shangLianLeft=this.canvas.width-this.canvas.fontSize-padding
  	shangLian.forEach((item,i) => {
  		if (i>max) {
  			ctx.fillText(item, shangLianLeft-this.canvas.fontSize-fontPadding, fromTop+((i-max-1)*(this.canvas.fontSize+fontPadding)))
  		}else{
  			ctx.fillText(item, shangLianLeft, fromTop+(i*(this.canvas.fontSize+fontPadding)));
  		}
  		
  	})
  	let xiaLian=this.canvas.xiaLian.split('')
  	let xiaLianLeft=padding
  	xiaLian.forEach((item,i) => {
  		if(i>max){
  			ctx.fillText(item, xiaLianLeft+this.canvas.fontSize+fontPadding, fromTop+((i-max-1)*(this.canvas.fontSize+fontPadding)))
  		}else{
  			ctx.fillText(item, xiaLianLeft, fromTop+(i*(this.canvas.fontSize+fontPadding)))
  		}
  		
  	})
  }
}
</script>

<style >
	#couplet{
		background:#ff0101;
		background:url(../assets/img/bg.jpg);
	}
	@font-face {   
	  font-family: xingshu; /*这里是说明调用来的字体名字*/   
	  src: url('../assets/font/xingshu.ttf'); /*这里是字体文件路径*/   
	}  
</style>

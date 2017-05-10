<template>
	<div>
		<header class="header-bar">
			<div class="left-icon-group">豆瓣</div>
			<h2 class="header-title" :class="titleAlign">
				<nav>
					<router-link href="#" to="/movie" v-for="item in navList" :style='{color : item.color}'>{{item.name}}</router-link>
				</nav>
			</h2> 
			<div class="right-icon-group" >
				<a href="javascript:;" @click="showSearch($event)">
					<img src="../../assets/images/search.png" alt="">
				</a>
			</div>
		</header>
		<div class="searchBox"  v-show="searchFlag">
			<header class="searchHeader">
				<a href="jaascript:;" @click="showSearch($event)">关闭</a>
				<input type="text">
			</header>
			<div class="content">
				<section>
					
				</section>
				<div class="navBottom">
					<div class="nav-item">
						<a class="toReg" href="#">注册帐号</a>
						<a class="toLogin" href="#">登录豆瓣</a>
					</div>
					<div class="nav-item">
						<a class="toPC" href="#">使用桌面版</a>
						<a class="toApp">使用豆瓣App</a>
					</div>
				</div>
			</div>
		</div>
	</div>
</template>

<script>

	export default {
		props : {
			titleAlign : {
				type : String,
				default : "center"
			}
		},
		template : "#header-template",
		data (){
			return {
				navList : [
					{
						name : "电影",
						color : "#2384E8"
					},
					{
						name : "图书",
						color : "#9F7860"
					},
					{
						name : "广播",
						color : "#E4A813"
					},
					{
						name : "小组",
						color : "#2AB8CC"
					}
				],
				searchFlag:false
			}
		},
		methods:{
			showSearch(e){
				this.searchFlag =!this.searchFlag;
			},
		}
	};
</script>
<style lang="less" scoped>
	.searchBox{
		background: #fff;
		position:absolute;
		top: 0;
		left: 0;
		bottom: 0;
		right:0 ;
		z-index: 100;
		header{
			height: 0.44rem;
			font-size: 0.15rem;
			line-height: 0.44rem;
			background: #fff;
			width: 100%;
			left: 0;
			top: 0;
			z-index: 100;
			display: -webkit-box;
			-webkit-box-align:center;
			&:after{
				content : "";
				height: 1px;
				background: #000;
				width: 200%;
				display: block;
				transform: scale(0.5);
				position: absolute;
				bottom: 0;
				left: -50%;
			};
			a{
				display: block;
				height: 100%;
				padding: 0 0.1rem;
				line-height: 0.44rem;
				color: #42bd56; 
				text-decoration: none;
			}
			input{
				display: block;
				-webkit-box-flex:1;
				border:0;
				height: 0.31rem;
				border-radius: 0.03rem;
				margin: 0 0.2rem;
				background: url(../../assets/images/sar.png) no-repeat #eee;
				background-size:0.17rem;

			}
		}
	}
	.header-bar{
		height: 0.44rem;
		font-size: 0.15rem;
		line-height: 0.44rem;
		background: #fff;
		position: fixed;
		width: 100%;
		left: 0;
		top: 0;
		z-index: 100;
		&:after{
			content : "";
			height: 1px;
			background: #000;
			width: 200%;
			display: block;
			transform: scale(0.5);
			position: absolute;
			bottom: 0;
			left: -50%;
		}; 
		.left-icon-group{
			float:left;
			height: 100%;
			padding: 0 0.1rem;
			position: relative;
			z-index: 20;
			color: #35943a;
			font-size: 0.22rem;
			font-weight: bolder;
		}
		.right-icon-group{
			float:right;
			height: 100%;
			padding: 0.1rem 0;
			padding-left: 1rem;
			position: relative;
			z-index: 20;
			img{
				position: absolute;
				right: 0.05rem;
				width: 30%;
			}
		}
		.header-title{
			position: absolute;
			z-index: 10;
			left: 1rem;
			display: -webkit-box;
			nav{
				display: block;
				a{
					padding: 0 0.1rem;
					text-decoration: none;
				}
			}
			&.center{
				-webkit-box-pack: center;
			}
			&.left{
				-webkit-box-pack: start;
			}
			&.right{
				-webkit-box-pack: end;
			}
		}
	}
</style>
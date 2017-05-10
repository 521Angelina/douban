<template>
	<div class="newsItem">
		<div class="newsItemConent" >
			<div class="photos" v-if="type == 3">
				<div class="leftPhotos" :style='{ backgroundImage:"url("+photo+")"}'>
					<div></div>
				</div>
				<div class="rightPhotos">
					<div :style='{ backgroundImage:"url("+photo+")"}'>
						<div></div>
					</div>
					<div :style='{ backgroundImage:"url("+photo+")"}'>
						<div></div>
					</div>
				</div>
			</div>
			<div class="rightConent" v-if="type == 1" :style='{ backgroundImage:"url("+photo+")"}'>
				<div>
					
				</div>
			</div>
			<div class="leftConent" v-if="type == 2">
				<h2>{{ title }}</h2>
				<p>{{ msg }}</p>
			</div>
		</div>
			
	</div>
</template>
<style lang="less" scoped>
	.newsItem{
		width: 100%;
		.newsItemConent{
			overflow: hidden;
			padding:0.15rem 0rem;
			position:relative;
			&:after{
				content : "";
				height: 1px;
				background: #d8d8d8;
				width: 200%;
				display: block;
				transform: scale(0.5);
				position: absolute;
				bottom: 0;
				left: -50%;
				margin-left: 0.12rem;
			};
			.leftConent{
				h2 {
				    text-align: justify;
				    font-size: 0.17rem;
				    font-weight: 500;
				    line-height: 1.41;
				    color: #494949;
				    margin-bottom:0.06rem;
				}
				p {
				    color: #aaa;
				    font-size: 12px;
				    line-height: 1.5;
				    display: -webkit-box;
				    overflow: hidden;
				    -webkit-box-orient: vertical;
				    -webkit-line-clamp:2;
				}
			}
			.rightConent{
				width: 30%;
				float: right;
				margin-left:0.2rem;
				background-size: cover;
				background-position: center center;
				div{
					padding-top: 100%;
				}
			}
			.photos{
				width: 100%;
				overflow: hidden;
				.leftPhotos{
					width: 80%;
					float: left;
					padding-right: 0.02rem;
					box-sizing:border-box;
					background-clip: content-box;
					background-size: cover;
					div{
						padding-top: 50%;
					}
				}
				.rightPhotos{
					width: 20%;
					float: left;
					div{
						width: 100%;
						padding-right: 0.02rem;	
						background-size: cover;	
						div{
							padding-top: 100%;
						}
					}
				}
			}
		}
	}
</style>
<script>
export default{
	props:{
		title:{
			type:String,
			default:""
		},
		msg:{
			type:String,
			default:""
		},
		photo:{
			type:String,
			default:""
		},
		photos:{
			type:Array,
			default:function(){}
		},
		type:{
			type:Number,
			default:1
		}
	}
}
</script>
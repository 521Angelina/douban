<template>
	<div class="page home-page">
		<ul class="quick-nav">
            <li>
                <a href="#">影院热映</a>
            </li>
            <li>
                  <a href="#">同城活动</a>
            </li>
            <li>
                <a id="hot-topics" href="#">北岛和朋友们的诗歌课</a>
            </li>
            <li>
                <a href="#">使用豆瓣App</a>
            </li>
        </ul>
        <div class="news-section">
        	<news-list v-for="item in homeData" 
	        	:kye="item.id" 
	        	:title="item.title" 
	        	:msg="item.target.desc"
        	></news-list>
        </div>
    </div>
</template> 
<script>
	import newsList from '@/components/base/newList';
	import homeData from '@/assets/data/home.json'
	export default{
		data(){
			return {
				homeData:homeData.recommend_feeds
			}
		},
		components:{
			newsList

		}
	 }
</script>
<style lang="less" scoped>
	.quick-nav {
	    overflow: hidden;
	    margin: 0.2rem 0 0 0;
	    padding-top: 0.06rem;
	    li {
		    float: left;
		    width: 50%;
		    padding: 0.03rem;
		    box-sizing: border-box;
		    font-size:15px;
		    a {
			    background-color: #f6f6f6;
			    color: #494949;
			    display: block;
			    text-align: center;
			    line-height: 0.2rem;
			    padding: 0.12rem 0;
			    border-radius: 0.02rem;
			    max-width: 100%;
			    overflow: hidden;
			    text-overflow: ellipsis;
			    white-space: nowrap;
			    word-wrap: normal;
			}
		}
	}
	.news-section{
		margin: 0 0.1rem;
	}
</style>
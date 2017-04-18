<template>
	<div class="slider">
		<div>
			<div class="title-wrapper">
				<span class="line"></span>
				<span class="title">{{worker.name}}</span>
				<span class="line"></span>
			</div>
			<div class="subhead">{{worker.style}}</div>
		</div>
		<div class="img-wrapper">
			<img :src="worker.img" />
		</div>
		<ul class="info-wrapper">
			<!--<li class="line">
				<div class="label">项目标题:</div>
				<div class="text">{{worker.name}}</div>
			</li>-->
			<!--<li class="line">
				<div class="label">项目类型:</div>
				<div class="text">{{worker.style}}</div>
			</li>-->
			<li class="line">
				<div class="label">核心技术:</div>
				<div class="text">{{worker.skills}}</div>
			</li>
			<li class="line" v-show="worker.funs">
				<div class="label">功能模块:</div>
				<div class="text">{{worker.funs}}</div>
			</li>
		</ul>
		<a class="btn" :href="worker.url">
			<img :src="worker.btn" />
			<span class="text">点击查看</span>
		</a>
	</div>
</template>

<script type="text/ecmascript-6">
	export default {
		props: {
			worker: {
				type: Object,
				default: {}
			}
		}
	}
</script>

<style type="text/css" lang="less" scoped>
	ul {
		list-style: none;
		margin: 0;
		padding: 0;
	}
	
	a,
	a:hover,
	a:visited,
	a:active {
		text-decoration: none;
		color: #fff;
	}
	.subhead{
		color: #808080;
		text-align: center;
		margin-top: 5px;
	}
	.slider {
		display: flex;
		height: 100%;
		justify-content: space-around;
		flex-direction: column;
		.title-wrapper {
			display: flex;
			width: 80%;
			margin: 0 auto;
			.title {
				flex: 0 0 auto;
				font-size: 24px;
				line-height: 1;
				color: #333;
				padding: 0 10px;
			}
			.line {
				flex: 1;
				height: 1px;
				background-color: #333;
				margin-top: 11px;
			}
		}
		.img-wrapper {
			img {
				display: block;
				width: 100%;
			}
		}
		.info-wrapper {
			width: 85%;
			margin: 0 auto;
			.line {
				display: flex;
				line-height:1.2;
				.label {
					flex: 0 0 80px;
					color: #808080;
				}
				.text {
					flex: 1;
				}
				&:not(:last-child){
					margin-bottom: 5px;
				}
			}
		}
		.btn {
			position: relative;
			display: block;
			width: 130px;
			height: 50px;
			line-height: 40px;
			text-align: center;
			margin: 0 auto;
			img {
				display: block;
				width: 100%;
				height: 100%;
			}
			.text {
				position: absolute;
				top: 0;
				left: 0;
				width: 100%;
				height: 100%;
				color: #fff;
			}
		}
	}
</style>
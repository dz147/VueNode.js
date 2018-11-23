<template>
	
	<el-container>
		<el-header>小老弟您觉得我的LOGO如何？可评论</el-header>
		<el-container>
			<el-aside width="200px">
				<el-tree :data="data" :props="defaultProps" accordion @node-click="handleNodeClick">
				</el-tree>
			</el-aside>
			<el-main>
				<div id="app">
					<div id="nav">
					<router-link to="/home">Home</router-link> |
					<router-link to="/resume">resume</router-link>
					<router-link to="/about"> | about</router-link>
					</div>
					<img src="./assets/9dukeji.png" style="margin-left: -57px;"> 
					<router-view/>
				</div>
			</el-main>
		</el-container>
	</el-container>
</template>

<script>
	

	export default {
		name: 'app',
		components: {
		},
		data() {
			return {
				data: [{
					label: '首页',
					children: [{
						label: '博客园',
						children: [{
							label: 'java'
						}]
					},{
						label: 'Github',
						children: [{
							label: 'Vue'
						}]
					}]
				}, {
					label: '功能',
					children: [{
						label: '二级 2-1',
						children: [{
							label: '三级 2-1-1'
						}]
					}, {
						label: '二级 2-2',
						children: [{
							label: '三级 2-2-1'
						}]
					}]
				}, {
					label: '其他',
					children: [{
						label: '二级 3-1',
						children: [{
							label: '三级 3-1-1'
						}]
					}, {
						label: '二级 3-2',
						children: [{
							label: '三级 3-2-1'
						}]
					}]
				}],
				defaultProps: {
					children: 'children',
					label: 'label'
				}
			};
		},
		methods: {
			handleNodeClick(data) {
				console.log(data);
			}
		}
	};
</script>

<style>
	#app {
		width: 100%;
	}

	.inputTest{
		width: 400px;
		height: 400px;
		margin-top: -50px;
		margin: auto;
	}
	.cinput {
		margin-bottom: 1em;
	}
	.comList{
		width: 100%;
		height: 100px;
		text-align: left;
	}

	.cinput label {
		display: flex;
		margin: 1em 0;
	}

	.cinput label span {
		flex-basis: 100px;
	}

	.cinput input,
	textarea {
		flex: 1;
	}

	textarea {
		margin-top: 52px;
	}

	.cinput footer {
		text-align: right;
		margin-top: -100px;
	}


	.comment {
		padding: 1em;
		border-bottom: 1px solid #f0f0f0;
		display: flex;
	}

	.comment-author {
		color: steelblue;
		flex-basis: 80px;
	}

	.comment-delete {
		margin-right:10px;
	}

	.el-header,
	.el-footer {
		background-color: #634322;
		color: #FFFFFF;
		text-align: center;
		line-height: 60px;
	}

	.el-aside {
		background-color: #42B983;
		color: #333;
		text-align: center;
		line-height: 200px;
	}

	.el-main {
		background-color: cornsilk;
		color: #333;
		text-align: center;
		line-height: 160px;
	}

	body>.el-container {
		margin-bottom: 40px;
	}

	.el-container:nth-child(5) .el-aside,
	.el-container:nth-child(6) .el-aside {
		line-height: 260px;
	}

	.el-container:nth-child(7) .el-aside {
		line-height: 320px;
	}
</style>

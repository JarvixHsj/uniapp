<script>
	export default {
		onLaunch: function() {
			console.log('App Launch')
		},
		onShow: function() {
			console.log('App Show')
		},
		onHide: function() {
			console.log('App Hide')
		},
		globalData: {
			baseUrl: 'https://ddsp.w.brofirst.cn/',
			imageUrl: '../../static/image/',
			erweima: '',
			userpic: '',
			bg: '',
			userid: '',
		},
	}
</script>

<style lang="scss">
	/* 引用uview库 */
		@import "uview-ui/index.scss";
	/*每个页面公共css */
	/*每个页面公共css */
	uni-page-head {
		display: none !important;
	}
	    /deep/.u-border-bottom:after{
    border: 0;
}
</style>

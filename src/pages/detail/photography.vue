<template>
	<section>
		<HeaderComp>
			<img slot="header-title" src="../../assets/img/photo/photo_logo.png">
			<img slot="scroll-button" src="../../assets/img/arrow_down.png">
		</HeaderComp>
		<div class="main">
			<div class="map">
				<img src="../../assets/img/yue_map.png" class="responsive-img">
			</div>
			<div class="advantage">
				<img src="../../assets/img/photo/advantage.jpg" class="responsive-img">
			</div>
			<div class="row">
				<div class="col">
					<img src="../../assets/img/photo/global_travel.jpg" class="responsive-img">
				</div>
				<div class="col micro-film">
					<div>
						<img src="../../assets/img/photo/film_title.png" class="responsive-img">
					</div>
					<div class="video">
						<video id="yueVideo" poster="http://img14.360buyimg.com/shaidan/s645x515_jfs/t11830/122/255851217/99035/296021db/59eb164eN4722184d.jpg" src="http://1254456297.vod2.myqcloud.com/2f3b5ff4vodtransgzp1254456297/fb24bb029031868223371331575/v.f30.mp4" controls @play="handlePlayed"></video>
					</div>
					<div>
						<img src="../../assets/img/photo/film_footer.png">
					</div>
				</div>
			</div>
			<div class="native relative">
				<img src="../../assets/img/photo/native.jpg" class="responsive-img">
				<router-link to="native" class="more-link">
					<!-- <img src="../../assets/img/photo/more.png"> -->
				</router-link>
			</div>
			<div class="oversea relative">
				<img src="../../assets/img/photo/oversea.jpg" class="responsive-img">
				<router-link to="oversea" class="more-link oversea">
					<!-- <img src="../../assets/img/photo/more.png"> -->
				</router-link>
			</div>
			<div class="footer">
				<img src="../../assets/img/photo/photo_footer.jpg" class="responsive-img">
			</div>
		</div>
	</section>
</template>
<script>
	import HeaderComp from '@/components/Header'
	export default {
		components: {
			HeaderComp,
		},
		methods: {
			handlePlayed() {
				this.isPlayed = true;
				let yueVideo = document.getElementById('yueVideo');
				if(yueVideo && yueVideo.readyState) {
					yueVideo.play()
				} else {
					this.$message('该视频暂无法播放')
				}
			},
		},
		mounted() {
			window.scrollTo(0, 0);
		}
	}
</script>
<style scoped lang="scss">
	.full-header {
		background: url(../../assets/img/photo/photography_bg.jpg) no-repeat center;
  	background-size: cover;
	}
	.micro-film {
		display: flex;
	  flex-direction: column;
	  justify-content: space-around;
	  align-items: center;
    padding: 30px;
    background: #F5F4EF;
    .video {
    	width: 100%;
    	video {
    		width: 100%;
    	}
    }
  }
  .more-link {
  	position: absolute;
  	top: 0;
  	left: 0;
  	width: 100%;
  	height: 100%;
  	// &.oversea {
  	// 	top: 30%;
  	// 	left: 25%;
  	// 	height: 0;
  	// }
  }
  .row {
  	display: flex;
  	.col {
			width: 50%;
  	}
  }
</style>
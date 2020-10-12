<template>
	<div class="hello">
		<h1>cctv1 央视电视台</h1>
		<div class="video-wrap">
			<video-player
				class="vjs-custom-skin"
				:options="playerOptions"
			></video-player>
		</div>
	</div>
</template>

<script>
// require styles
import "video.js/dist/video-js.css";
import "vue-video-player/src/custom-theme.css";
import { videoPlayer } from "vue-video-player";
// rtmp video-flash
import "videojs-flash";
export default {
	name: "HelloWorld",
	components: {
		videoPlayer,
	},
	data() {
		return {
			playerOptions: {
				height: "400",
				language: "en",
				playbackRates: [0.5, 1.0, 1.5, 2.0],
				sources: [
					{
						type: "rtmp/mp4",
						src: "rtmp://58.200.131.2:1935/livetv/cctv1",
					},
				],
				techOrder: ["flash"],
				autoplay: true,
				controls: true,
				poster: "",
				notSupportedMessage: "不支持的视频格式",
			},
		};
	},
};
</script>

<style scoped>
.video-wrap {
	margin: 0 auto;
	width: 700px;
	/* height: 400px; */
}
</style>

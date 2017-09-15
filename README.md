# video
html获取video播放次数，循环播放n次后执行对应的方法
在前端项目中，有时我们会在视频播放完毕后执行一些操作，甚至是视频播放指定的次数后执行一些操作。

---------------------------------------------------------------------



<video id="video1" controls="controls"  autoplay='autoplay' width="100%">
			<source src="http://clips.vorwaerts-gmbh.de/big_buck_bunny.mp4" type="video/mp4">
</video>

myVid=document.getElementById("video1");
思维路径：不要在video上设置loop属性，等播放完毕再执行播放函数。
然后还要调用play()方法开启视频；这个方法是js的必须要用js去调用用jquery调用无效。
两个方法：
1）每次视频播放完毕时调用的方法
myVid.onended = function() 
	{	
	 console.log("音频已播放完成");
//	myVid.setAttribute('loop','true');//loop属性一定不要加，如果给video给了loop，那么无论循环多少次就是相当于只播放完毕了一次。
	playVid()
	};
2）播放视频函数，并且统计播放次数
var time=0;
    function playVid(){
	 time++;
	console.log("以播放"+time+"次");
	myVideo.play();
}

---------
两个不熟悉的方法：
onended:视频播放完毕执行的事件
play() 开启video的方法。

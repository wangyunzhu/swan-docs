---
title: 背景音频管理播放
header: develop
nav: api
sidebar: media_backgroundaudiomanager
---


## BackgroundAudioManager.onCanplay

**解释**：音频进入可以播放状态，但不保证后面可以流畅播放 。

**方法参数**：Function callback
 
**示例**：

<a href="swanide://fragment/1f2e51c17e86f21e8eb67b2894dcbf301573422228143" title="在开发者工具中预览效果" target="_self">在开发者工具中预览效果</a>

* 在 js 文件中

```javascript

Page({
    onShow() {
        const backgroundAudioManager = swan.getBackgroundAudioManager();
        backgroundAudioManager.title = '演员';
        backgroundAudioManager.epname = '演员';
        backgroundAudioManager.singer = '薛之谦';
        backgroundAudioManager.coverImgUrl = 'http://c.hiphotos.baidu.com/super/pic/item/8b13632762d0f703e34c0f6304fa513d2797c597.jpg';
        backgroundAudioManager.onCanplay(function(res) {
            console.log('backgroundAudioManager.onCanplay', res)
            swan.showModal({
                title: 'onCanplay success',
                content: JSON.stringify(res)
            })
        });
        this.backgroundAudioManager = backgroundAudioManager;
        this.backgroundAudioManager.src = 'http://vd3.bdstatic.com/mda-ic7mxzt5cvz6f4y5/mda-ic7mxzt5cvz6f4y5.mp3';
        this.backgroundAudioManager.play();
    }
});

```
 

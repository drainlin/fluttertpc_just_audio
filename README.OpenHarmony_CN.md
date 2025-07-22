> 模板版本: v0.0.1

<p align="center">
  <h1 align="center"> <code>just_audio</code> </h1>
</p>

本项目基于 [just_audio](https://pub.dev/packages/just_audio) 开发。

## 1. 安装与使用

### 1.1 安装方式

进入到工程目录并在 pubspec.yaml 中添加以下依赖：

<!-- tabs:start -->

#### pubspec.yaml

```yaml
...

dependencies:
  just_audio_ohos:
    git:
      url: https://gitcode.com/openharmony-sig/fluttertpc_just_audio
      path: just_audio/ohos

...
```

执行命令

```bash
flutter pub get
```

<!-- tabs:end -->

### 1.2 使用案例

使用案例详见 [just_audio/ohos/example](/just_audio/ohos/example/lib/main.dart)

## 2. 约束与限制

### 2.1 兼容性

在以下版本中已测试通过

1. Flutter: 3.7.12-ohos-1.0.6; SDK: 5.0.0(12); IDE: DevEco Studio: 5.0.13.200; ROM: 5.1.0.120 SP3;
2. Flutter: 3.22.1-ohos-1.0.1; SDK: 5.0.0(12); IDE: DevEco Studio: 5.0.13.200; ROM: 5.1.0.120 SP3;

## 3. API

> [!TIP] "ohos Support"列为 yes 表示 ohos 平台支持该属性；no 则表示不支持；partially 表示部分支持。使用方法跨平台一致，效果对标 iOS 或 Android 的效果。

| Name                                                 | Description                                                                           | Type     | Input                                                               | Output                                                                 | ohos Support |
|------------------------------------------------------|---------------------------------------------------------------------------------------|----------|---------------------------------------------------------------------|------------------------------------------------------------------------|--------------|
| init                                                 | 创建一个新的平台播放器并返回一个嵌套的平台接口用于与该播放器进行通信                                                    | function | InitRequest request                                                 | `Future<AudioPlayerPlatform>`                                          | yes          |
| disposePlayer                                        | 处理平台播放器                                                                               | function | DisposePlayerRequest request                                        | `Future<DisposePlayerResponse>`                                        | yes          |
| disposeAllPlayers                                    | 处理所有平台播放器                                                                             | function | DisposeAllPlayersRequest request                                    | `Future<DisposeAllPlayersResponse>`                                    | yes          |
| load                                                 | 加载音频源                                                                                 | function | LoadRequest request                                                 | `Future<LoadResponse>`                                                 | yes          |
| play                                                 | 在当前索引和位置播放当前音频源                                                                       | function | PlayRequest request                                                 | `Future<PlayResponse>`                                                 | yes          |
| pause                                                | 暂停播放                                                                                  | function | PauseRequest request                                                | `Future<PauseResponse>`                                                | yes          |
| setVolume                                            | 音量变化                                                                                  | function | SetVolumeRequest request                                            | `Future<SetVolumeResponse>`                                            | yes          |
| setSpeed                                             | 更改播放速度                                                                                | function | SetSpeedRequest request                                             | `Future<SetSpeedResponse>`                                             | yes          |
| setPitch                                             | 音调变化                                                                                  | function | SetPitchRequest request                                             | `Future<SetPitchResponse>`                                             | yes          |
| setSkipSilence                                       | 设置是否跳过静默                                                                              | function | /                                                                   | `Future<SetSkipSilenceResponse>`                                       | yes          |
| setLoopMode                                          | 设置循环播放模式                                                                              | function | SetLoopModeRequest request                                          | `Future<SetLoopModeResponse>`                                          | no           |
| setShuffleMode                                       | 设置随机播放模式                                                                              | function | SetShuffleModeRequest request                                       | `Future<SetShuffleModeResponse>`                                       | no           |
| setShuffleOrder                                      | 设置随机播放顺序                                                                              | function | SetShuffleOrderRequest request                                      | `Future<SetShuffleOrderResponse>`                                      | no           |
| setAutomaticallyWaitsToMinimizeStalling              | 在 iOS 和 macOS 上，设置 automaticallyWaitsToMinimizeStalling 选项，在其他平台上不执行任何操作              | function | SetAutomaticallyWaitsToMinimizeStallingRequest request              | `Future<SetAutomaticallyWaitsToMinimizeStallingResponse>`              | no           |
| setCanUseNetworkResourcesForLiveStreamingWhilePaused | 在 iOS 和 macOS 上，设置 canUseNetworkResourcesForLiveStreamingWhilePaused 选项，在其他平台上不执行任何操作 | function | SetCanUseNetworkResourcesForLiveStreamingWhilePausedRequest request | `Future<SetCanUseNetworkResourcesForLiveStreamingWhilePausedResponse>` | no           |
| setPreferredPeakBitRate                              | 在 iOS 和 macOS 上设置 preferredPeakBitRate 选项，在其他平台上不执行任何操作                               | function | SetPreferredPeakBitRateRequest request                              | `Future<SetPreferredPeakBitRateResponse>`                              | no           |
| setAllowsExternalPlayback                            | 在 iOS 和 macOS 上，设置 letsExternalPlayback 选项，在其他平台上不执行任何操作。                             | function | SetAllowsExternalPlaybackRequest request                            | `Future<SetAllowsExternalPlaybackResponse>`                            | no           |
| seek                                                 | 寻找给定的索引和位置                                                                            | function | SeekRequest request                                                 | `Future<SeekResponse>`                                                 | yes          |
| setAndroidAudioAttributes                            | 在 Android 上设置音频属性，在其他平台上不执行任何操作                                                       | function | SetAndroidAudioAttributesRequest request                            | `Future<SetAndroidAudioAttributesResponse>`                            | no           |
| dispose                                              | 由于 [JustAudioPlatform.disposePlayer] 未实现，此方法仍将被调用                                     | function | DisposeRequest request                                              | `Future<DisposeResponse>`                                              | no           |
| concatenatingInsertAll                               | 将音频源插入给定的连接音频源                                                                        | function | ConcatenatingInsertAllRequest request                               | `Future<ConcatenatingInsertAllResponse>`                               | yes          |
| concatenatingRemoveRange                             | 从给定的连接音频源中删除音频源                                                                       | function | ConcatenatingRemoveRangeRequest request                             | `Future<ConcatenatingRemoveRangeResponse>`                             | yes          |
| concatenatingMove                                    | 在串联音频源内移动音频源                                                                          | function | ConcatenatingMoveRequest request                                    | `Future<ConcatenatingMoveResponse>`                                    | yes          |
| audioEffectSetEnabled                                | 更改音频效果的状态                                                                             | function | AudioEffectSetEnabledRequest request                                | `Future<AudioEffectSetEnabledResponse>`                                | no           |
| androidLoudnessEnhancerSetTargetGain                 | 设置 Android 响度增强器的目标增益                                                                 | function | AndroidLoudnessEnhancerSetTargetGainRequest request                 | `Future<AndroidLoudnessEnhancerSetTargetGainResponse>`                 | no           |
| androidEqualizerGetParameters                        | 获取 Android 均衡器参数                                                                      | function | AndroidEqualizerGetParametersRequest request                        | `Future<AndroidEqualizerGetParametersResponse>`                        | no           |
| androidEqualizerBandSetGain                          | 设置 Android 均衡器频段的增益                                                                   | function | AndroidEqualizerBandSetGainRequest request                          | `Future<AndroidEqualizerBandSetGainResponse>`                          | no           |

## 4. 属性

> [!TIP] "ohos Support"列为 yes 表示 ohos 平台支持该属性；no 则表示不支持；partially 表示部分支持。使用方法跨平台一致，效果对标 iOS 或 Android 的效果。

### AudioPlayer

| Name                            | Description                    | Type                    | Input | Ouput | ohos Support |
|---------------------------------|--------------------------------|-------------------------|-------|-------|--------------|
| userAgent                       | 在所有 HTTP 请求上设置的用户代理            | String?                 | /     | /     | no           |
| handleInterruptions             | 是否手动处理音频中断                     | bool                    | /     | /     | no           |
| androidApplyAudioAttributes     | 控制是否将 AudioAttributes 应用于音频播放器 | bool                    | /     | /     | no           |
| handleAudioSessionActivation    | just_audio 是否在播放音频时自动激活音频会话    | bool                    | /     | /     | no           |
| audioLoadConfiguration          | 默认音频加载和缓冲行为                    | AudioLoadConfiguration? | /     | /     | no           |
| audioPipeline                   | 用于配置音频处理管道                     | AudioPipeline?          | /     | /     | no           |
| androidOffloadSchedulingEnabled | 启用 Android 音频离线调度              | bool                    | /     | /     | no           |
| useProxyForRequestHeaders       | 允许支持的平台直接发送请求标头，而无需使用代理        | bool                    | /     | /     | no           |

## 5. 遗留问题

- [ ] ohos 端无音频裁剪能力: [issue#21](https://gitcode.com/openharmony-sig/fluttertpc_just_audio/issues/21)
- [ ] ohos 端无音频合成能力: [issue#21](https://gitcode.com/openharmony-sig/fluttertpc_just_audio/issues/21)
- [ ] ohos 端无网络音频或取元数据能力: [issue#21](https://gitcode.com/openharmony-sig/fluttertpc_just_audio/issues/21)
- [ ] ohos 端无设置音调能力: [issue#21](https://gitcode.com/openharmony-sig/fluttertpc_just_audio/issues/21)
- [ ] ohos 端无均衡器设置: [issue#21](https://gitcode.com/openharmony-sig/fluttertpc_just_audio/issues/21)
- [ ] ohos 端无音效增强能力: [issue#21](https://gitcode.com/openharmony-sig/fluttertpc_just_audio/issues/21)

## 6. 其他

## 7. 开源协议

本项目基于 [The MIT License (MIT)](/LICENSE) ，请自由地享受和参与开源。

> Template version: v0.0.1

<p align="center">
  <h1 align="center"> <code>just_audio</code> </h1>
</p>

This project is based on [just_audio](https://pub.dev/packages/just_audio/versions).

## 1. Installation and Usage

### 1.1 Installation

Go to the project directory and add the following dependencies in pubspec.yaml

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

Execute Command

```bash
flutter pub get
```

<!-- tabs:end -->

### 1.2 Usage

For use cases [just_audio/ohos/example](/just_audio/ohos/example/lib/main.dart)

## 2. Constraints

### 2.1 Compatibility

This document is verified based on the following versions:

1. Flutter: 3.7.12-ohos-1.0.6; SDK: 5.0.0(12); IDE: DevEco Studio: 5.0.13.200; ROM: 5.1.0.120 SP3;
2. Flutter: 3.22.1-ohos-1.0.1; SDK: 5.0.0(12); IDE: DevEco Studio: 5.0.13.200; ROM: 5.1.0.120 SP3;

## 3. API

> [!TIP] If the value of **ohos Support** is **yes**, it means that the ohos platform supports this property; **no** means the opposite; **partially** means some capabilities of this property are supported. The usage method is the same on different platforms and the effect is the same as that of iOS or Android.

| Name                                                 | Description                                                                                                              | Type     | Input                                                               | Output                                                                 | ohos Support |
|------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------|----------|---------------------------------------------------------------------|:-----------------------------------------------------------------------|--------------|
| init                                                 | Creates a new platform player and returns a nested platform interface for communicating with that player                 | function | InitRequest request                                                 | `Future<AudioPlayerPlatform> `                                         | yes          |
| disposePlayer                                        | Disposes of a platform player                                                                                            | function | DisposePlayerRequest request                                        | `Future<DisposePlayerResponse>`                                        | yes          |
| disposeAllPlayers                                    | Disposes of all platform players                                                                                         | function | DisposeAllPlayersRequest request                                    | `Future<DisposeAllPlayersResponse>`                                    | yes          |
| load                                                 | Loads an audio source                                                                                                    | function | LoadRequest request                                                 | `Future<LoadResponse>`                                                 | yes          |
| play                                                 | Plays the current audio source at the current index and position                                                         | function | PlayRequest request                                                 | `Future<PlayResponse>`                                                 | yes          |
| pause                                                | Pauses playback                                                                                                          | function | PauseRequest request                                                | `Future<PauseResponse>`                                                | yes          |
| setVolume                                            | Changes the volume                                                                                                       | function | SetVolumeRequest request                                            | `Future<SetVolumeResponse>`                                            | yes          |
| setSpeed                                             | Changes the playback speed                                                                                               | function | SetSpeedRequest request                                             | `Future<SetSpeedResponse>`                                             | yes          |
| setPitch                                             | Changes the pitch                                                                                                        | function | SetPitchRequest request                                             | `Future<SetPitchResponse>`                                             | yes          |
| setSkipSilence                                       | Sets skipSilence to true/false                                                                                           | function | /                                                                   | `Future<SetSkipSilenceResponse>`                                       | yes          |
| setLoopMode                                          | Sets the loop mode                                                                                                       | function | SetLoopModeRequest request                                          | `Future<SetLoopModeResponse>`                                          | no           |
| setShuffleMode                                       | Sets the shuffle mode                                                                                                    | function | SetShuffleModeRequest request                                       | `Future<SetShuffleModeResponse>`                                       | no           |
| setShuffleOrder                                      | Sets the shuffle order                                                                                                   | function | SetShuffleOrderRequest request                                      | `Future<SetShuffleOrderResponse>`                                      | no           |
| setAutomaticallyWaitsToMinimizeStalling              | On iOS and macOS, sets the automaticallyWaitsToMinimizeStalling option and does nothing on other platforms               | function | SetAutomaticallyWaitsToMinimizeStallingRequest request              | `Future<SetAutomaticallyWaitsToMinimizeStallingResponse>`              | no           |
| setCanUseNetworkResourcesForLiveStreamingWhilePaused | On iOS and macOS, sets the canUseNetworkResourcesForLiveStreamingWhilePaused option, and does nothing on other platforms | function | SetCanUseNetworkResourcesForLiveStreamingWhilePausedRequest request | `Future<SetCanUseNetworkResourcesForLiveStreamingWhilePausedResponse>` | no           |
| setPreferredPeakBitRate                              | On iOS and macOS, sets the preferredPeakBitRate option, and does nothing on other platforms                              | function | SetPreferredPeakBitRateRequest request                              | `Future<SetPreferredPeakBitRateResponse>`                              | no           |
| setAllowsExternalPlayback                            | On iOS and macOS, sets the allowsExternalPlayback option, and does nothing on other platforms.                           | function | SetAllowsExternalPlaybackRequest request                            | `Future<SetAllowsExternalPlaybackResponse>`                            | no           |
| seek                                                 | Seeks to the given index and position                                                                                    | function | SeekRequest request                                                 | `Future<SeekResponse>`                                                 | yes          |
| setAndroidAudioAttributes                            | On Android, sets the audio attributes, and does nothing on other platforms                                               | function | SetAndroidAudioAttributesRequest request                            | `Future<SetAndroidAudioAttributesResponse>`                            | no           |
| dispose                                              | This method will still be called as a [JustAudioPlatform.disposePlayer] is not implemented                               | function | DisposeRequest request                                              | `Future<DisposeResponse>`                                              | no           |
| concatenatingInsertAll                               | Inserts audio sources into the given concatenating audio source                                                          | function | ConcatenatingInsertAllRequest request                               | `Future<ConcatenatingInsertAllResponse>`                               | yes          |
| concatenatingRemoveRange                             | Removes audio sources from the given concatenating audio source                                                          | function | ConcatenatingRemoveRangeRequest request                             | `Future<ConcatenatingRemoveRangeResponse>`                             | yes          |
| concatenatingMove                                    | Moves an audio source within a concatenating audio source                                                                | function | ConcatenatingMoveRequest request                                    | `Future<ConcatenatingMoveResponse>`                                    | yes          |
| audioEffectSetEnabled                                | Changes the enabled status of an audio effect                                                                            | function | AudioEffectSetEnabledRequest request                                | `Future<AudioEffectSetEnabledResponse>`                                | no           |
| androidLoudnessEnhancerSetTargetGain                 | Sets the target gain on the Android loudness enhancer                                                                    | function | AndroidLoudnessEnhancerSetTargetGainRequest request                 | `Future<AndroidLoudnessEnhancerSetTargetGainResponse>`                 | no           |
| androidEqualizerGetParameters                        | Gets the Android equalizer parameters                                                                                    | function | AndroidEqualizerGetParametersRequest request                        | `Future<AndroidEqualizerGetParametersResponse>`                        | no           |
| androidEqualizerBandSetGain                          | Sets the gain for an Android equalizer band                                                                              | function | AndroidEqualizerBandSetGainRequest request                          | `Future<AndroidEqualizerBandSetGainResponse>`                          | no           |

## 4. Properties

> [!TIP] If the value of **ohos Support** is **yes**, it means that the ohos platform supports this property; **no** means the opposite; **partially** means some capabilities of this property are supported. The usage method is the same on different platforms and the effect is the same as that of iOS or Android.

### AudioPlayer

| Name                            | Description                                                                             | Type                    | Input | Ouput | ohos Support |
|---------------------------------|-----------------------------------------------------------------------------------------|-------------------------|-------|-------|--------------|
| userAgent                       | The user agent to set on all HTTP requests                                              | String?                 | /     | /     | no           |
| handleInterruptions             | Whether handle audio interruptions manually                                             | bool                    | /     | /     | no           |
| androidApplyAudioAttributes     | Controls whether AudioAttributes are applied to the audio player                        | bool                    | /     | /     | no           |
| handleAudioSessionActivation    | Whether just_audio to automatically activate the audio session when playing audio       | bool                    | /     | /     | no           |
| audioLoadConfiguration          | The default audio loading and buffering behaviour                                       | AudioLoadConfiguration? | /     | /     | no           |
| audioPipeline                   | Used to configure the audio processing pipeline                                         | AudioPipeline?          | /     | /     | no           |
| androidOffloadSchedulingEnabled | Enable Android audio offline scheduling                                                 | bool                    | /     | /     | no           |
| useProxyForRequestHeaders       | Allow supported platforms to send the request headers directly without use of the proxy | bool                    | /     | /     | no           |

## 5. Known Issues

- [ ] ohos has no audio trimming capability: [issue#21](https://gitcode.com/openharmony-sig/fluttertpc_just_audio/issues/21)
- [ ] ohos has no audio synthesis capability: [issue#21](https://gitcode.com/openharmony-sig/fluttertpc_just_audio/issues/21)
- [ ] ohos has no network audio or metadata acquisition capability: [issue#21](https://gitcode.com/openharmony-sig/fluttertpc_just_audio/issues/21)
- [ ] ohos has no pitch setting capability: [issue#21](https://gitcode.com/openharmony-sig/fluttertpc_just_audio/issues/21)
- [ ] ohos has no equalizer setting capability: [issue#21](https://gitcode.com/openharmony-sig/fluttertpc_just_audio/issues/21)
- [ ] ohos has no sound enhancement capability: [issue#21](https://gitcode.com/openharmony-sig/fluttertpc_just_audio/issues/21)

## 6. Others

## 7. License

This project is licensed under [The MIT License (MIT)](/LICENSE).

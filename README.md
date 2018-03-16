# VideoCast-Swift

VideoCast-Swift is a framework for broadcasting live video. It is based on [VideoCore](https://github.com/jgh-/VideoCore-Inactive) C++ library but rewritten in Swift. It currently works with iOS. It is a work in progress and will eventually expand to other platforms such as OS X.

### Table of Contents
* [Setup](#setup)
* [Architecture Overview](#architecture-overview)
* [Features](#features)
* [Version History](#version-history)

## Setup

#### CocoaPods

Create a `Podfile` with the contents
``` ruby
platform :ios, '10.0'
pod 'VideoCore', '~> 0.0.1'
use_frameworks!
```
Next, run `pod install` and open the `xcworkspace` file that is created.

## Architecture Overview

Samples start at the source, are passed through a series of transforms, and end up at the output.

e.g. Source (Camera) -> Transform (Composite) -> Transform (H.264 Encode) -> Transform (RTMP Packetize) -> Output (RTMP)

## Features

 - Streaming protocols
   - RTMP publish
   - SRT
 - Encoders
   - H.264
   - HEVC
   - AAC
 - Multiplexers
   - MPEG-2 TS
   - MP4 for recording
 - Mixers
   - Video
   - Audio
 - Sources
   - Camera
   - Microphone

## Build SRT

```
git clone https://github.com/openfresh/VideoCast-Swift.git
cd VideoCast-Swift

git submodule update --init

cd SRT
./build_openssl.sh 
./build_srt.sh

```

## Version History

* 0.1.0 
	* Initial CocoaPods version

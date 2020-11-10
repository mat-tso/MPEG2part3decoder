# Yet an other MPEG-2 decoder
An attempt at an MPEG-2 decoder in Rust.

This is a toy project, use at your own risk!

## Supported layers
 - [ ] Layer I (MP1)
 - [ ] Layer II (MP2)
 - [ ] Layer III (MP3)

## Personal goals
 - Learn Rust
 - Learn MP3 file format
 - Learn audio signal processing
 
## Implementation goals
 - Use safe Rust as much as possible
 - No panic possible
 - 100% coverage
 
## Features
 - [ ] Dump MPEG-2 structure
 - [ ] Dump MPEG-2 packets
 - [ ] Output PCM
  
## Test goals
 - [ ] Compare struct dump to reference
 - [ ] Compare packets dump to reference
 - [ ] PCM output is identical to reference excluding rounding errors
 - [ ] Streatch: Assembly generated never calls `panic!`
 
 Reference should be generatable from `fmprobe` and `ffmpeg`

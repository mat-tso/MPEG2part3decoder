# Yet an other mp3 decoder
An attempt at an mp3 decoder in Rust.


This is a toy project, use at your own risk!

## Personal goals
 - Learn Rust
 - Learn MP3 file format
 - Learn audio signal processing
 
## Implementation goals
 - Use safe Rust as much as possible
 - No panic possible
 - 100% coverage
 
## Features
 - [ ] Dump MP3 structure
 - [ ] Dump MP3 packets
 - [ ] Output PCM
  
## Test goals
 - [ ] Compare struct dump to reference
 - [ ] Compare packets dump to reference
 - [ ] PCM output is identical to reference excluding rounding errors
 - [ ] Assembly generated never calls `panic!`
 
 Reference should be generatable from `fmprobe` and `ffmpeg`

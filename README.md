# Yet another MPEG-2 decoder
An attempt at an MPEG-2 decoder in Rust.

This is a toy project, use at your own risk!

## Supported layers
 - [ ] Layer I (MP1)
 - [ ] Layer II (MP2)
 - [ ] Layer III (MP3)

## Roadmap
 1) [ ] Find a simple [reference implementation](#existing-implementations)
      + It should be in C and contain as few as possible assembly and no threading
      + It should have a compatible license
      + It should have a test suite
      + It should be simple to read and port (no assembly, no complex SIMD)
 2. [ ] Compile the reference implementation as submodule with Cargo
 3. [ ] Make the reference implementation callable from Rust
 4. [ ] Reimplement each component and compare with reference implementation

Layer I being so simple, the reference implementation may be 

## Personal goals
 - Learn Rust
 - Learn MP3 file format
 - Learn audio signal processing
 
## Safety goals
 - Use safe Rust as much as possible
 - No explicit panic
 
## Features
 - [ ] Dump MPEG-2 structure
 - [ ] Dump MPEG-2 packets
 - [ ] Output PCM
  
## Test goals
 - [ ] 100% test coverage
 - [ ] Compare struct dump to reference
 - [ ] Compare packets dump to reference
 - [ ] PCM output is identical to reference excluding rounding errors
 - [ ] Stretch: Assembly generated never calls `panic!`
 
 Reference should be generatable from `fmprobe` and `ffmpeg`.

 
## Existing implementations

    
| Implementation   | SIMD | Layer | License | ISO |
| ---------------- |:----:|:-----:|:-------:|:----|
| [PDMP2]          | [ ]  |  II   |  CC0    | [?] |
| [TwoLame]        | [?]  |  II   |  LGPL   | [X] |
| [mp3-decoder]    | [ ]  |  III  |  GPL    | [ ] |
| [minimp3]        | [X]  |  All  |  CC0    | [X] |
| [libmad]         | [X]  |  All  |  GPL    | [X] |

[PDMP2]: https://github.com/technosaurus/PDMP2
[TwoLame]: https://github.com/njh/twolame
[mp3-decoder]: https://github.com/FlorisCreyf/mp3-decoder
[minimp3]: https://github.com/lieff/minimp3
[libmad]: https://github.com/markjeee/libmad

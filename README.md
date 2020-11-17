# Yet another MPEG-2 Part 3 decoder
An attempt at an [MPEG-2 Part 3](https://en.wikipedia.org/wiki/MPEG-2_Part_3) decoder in Rust.

This is a toy project, use at your own risk!

## Supported layers
 - [ ] [Layer I] (MP1)
 - [ ] [Layer II] (MP2)
   + [ ] [Multichannel]
 - [ ] [Layer III] (MP3)

[Layer I]: https://en.wikipedia.org/wiki/MPEG-1_Audio_Layer_I
[Layer II]: https://en.wikipedia.org/wiki/MPEG-1_Audio_Layer_II
[Multichannel]: https://en.wikipedia.org/wiki/MPEG_Multichannel
[Layer III]: https://en.wikipedia.org/wiki/MPEG-1_Audio_Layer_III

## Roadmap
 1) [ ] Find a simple [reference implementation](#existing-implementations)
      + It should be in C and contain as few as possible assembly and no threading
      + It should have a compatible license
      + It should have a test suite
      + It should be simple to read and port (no assembly, no complex SIMD)
 2. [ ] Compile the reference implementation as submodule with Cargo
 3. [ ] Make the reference implementation callable from Rust ([C2Rust](https://github.com/immunant/c2rust)?)
 4. [ ] Reimplement each component and compare with reference implementation

Layer I being so simple, a reference implementation may not be needed.

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

    
| Implementation   | SIMD | Layer | License | ISO | Note
| ---------------- |:----:|:-----:|:-------:|:---:|:------|
| [Jon Olick]'s    | [ ]  |  I    |  Public | [?] | [JO archive]
| [PDMP2]          | [ ]  |  II   |  Zlib   | [?] |
| [mp3-decoder]    | [ ]  |  III  |  GPL    | [ ] |
| [minimp3]        | [X]  |  All  |  CC0    | [X] |
| [libmad]         | [X]  |  All  |  GPL    | [X] |
| [PDMP3]          | [ ]  | All?  |  CC0    | [?] |
| ~[TwoLame]~      | [?]  |  II   |  LGPL   | [X] | Encoder only

[Jon Olick]: https://www.jonolick.com/uploads/7/9/2/1/7921194/jo_mp1.cpp
[JO archive]: https://github.com/dying153/jonolick.com/blob/master/code/jo_mp1.cpp
[PDMP2]: https://github.com/technosaurus/PDMP2
[PDMP3]: https://github.com/technosaurus/PDMP3
[mp3-decoder]: https://github.com/FlorisCreyf/mp3-decoder
[minimp3]: https://github.com/lieff/minimp3
[libmad]: https://github.com/markjeee/libmad
[TwoLame]: https://github.com/njh/twolame

## Interesting links
- [Let’s build an MP3-decoder!](http://blog.bjrn.se/2008/10/lets-build-mp3-decoder.html)
- [Inside MP3](http://www.multiweb.cz/twoinches/mp3inside.htm)
- [Inside the MP3 codec](http://www.mp3-converter.com/mp3codec/)
- [minimp3 interesting links](https://github.com/lieff/minimp3#interesting-links)
- [PDMP3 interesting links](https://github.com/technosaurus/PDMP3#todo:~:text=good%20references)

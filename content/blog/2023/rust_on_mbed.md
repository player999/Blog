title=Opinion on Embedded Rust as of 2023
date=2023-11-26
type=post
tags=blog
status=published
~~~~~~
It is not ready yet. I had experience with RP2040 chip and would like to share it
Here several of my points why it is not ready:
1. Without std library there is not so many useful applications. Especially if to talk about http server
2. Feature flags compatibility and configuration on Rust is a nightmare!
3. Constant need to wrap code that accessing HW into unsafe block. I have so many of such wraps that the unsafe block loses it's original purpose

Bottom lines. If you want to use Rust in embedded applications, be sure to have std library support. ESP32 (not ESP8266 unfortunately) has such. Also maybe it is not so good idea -- to write everything on Rust.
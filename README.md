# Gameboy.Live websockets

*This fork as already been merged into the main [Gameboy.Live repo](https://github.com/HFO4/gameboy.live).*
---

This is a fork of [Gameboy.Live](https://github.com/HFO4/gameboy.live) that implements a websockets interface for sending static images so that you don't need to reload the website after
each button press. Full documentation of Gameboy.Live is on its [Github page](https://github.com/HFO4/gameboy.live).

Note: this is still under development.

### Build

```
go build -o gbdotlive main.go
```

### Communicating via websockets

You set up a static cloud gaming server, where one specific game is emulated with folowing command:

```
gbdotlive -S -r "Pokemon - Red Version (USA, Europe) (SGB Enhanced).gb" 
```

A HTTP server will start up on default port `1989`.
- Use `ws://localhost:1989/stream` route in order to start a websocket communication channel.
- Images will be streamed to the client in PNG encoding.
- The client can send their input commands in text format using one of these codes:
    - Right Arrow: `0` 
    - Left Arrow: `1`
    - Up Arrow: `2`
    - Down Arrow: `3`
    - A: `4`
    - B: `5`
    - Select: `6`
    - Start: `7`
- check out `client_demo.html` for a simple demo and don't forget to run the server before by using the command above &#x1F31D;

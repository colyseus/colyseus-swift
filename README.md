# Colyseus SDK for Swift

Swift over the [Colyseus native SDK](https://github.com/colyseus/native-sdk),
for macOS, iOS and tvOS.

```swift
.package(url: "https://github.com/colyseus/colyseus-swift", from: "0.18.2")
```

```swift
let client = try Colyseus.Client(endpoint: "ws://localhost:2567")
let room = try await client.joinOrCreate("my_room", state: MyRoomState.self)

let callbacks = Colyseus.Callbacks.get(room)
callbacks.onAdd(room.state!.players) { sessionId, player in
    spawn(sessionId, at: player.x, player.y)
}
```

The frame loop, the prediction layer and the rest of the API are documented in
[platforms/swift/README.md](https://github.com/colyseus/native-sdk/blob/main/platforms/swift/README.md).

---

> **This repository is generated.** It is published from
> [colyseus/native-sdk](https://github.com/colyseus/native-sdk)'s
> `platforms/swift` on every release, and `main` is rewritten each time — a
> commit made here would be overwritten.
>
> **Issues and pull requests belong in
> [colyseus/native-sdk](https://github.com/colyseus/native-sdk/issues).**

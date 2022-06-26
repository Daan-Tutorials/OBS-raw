# OBS raw


(with streamer.bot)

[Offical documentain](https://github.com/obsproject/obs-websocket/blob/4.x-current/docs/generated/protocol.md)

---

## How does OBS raw work?

OBS raw is a JSON coding language, where you can change/get properties of OBS things. The things that you request doesn't have to be sources it can be anything OBS related.

### How does it look like?

Here a basic example.

```json
{
"request-type": "TheRequestType",
"sceneName": "your scene name",
"sourceSettings": {
  "color": 4279410288,
  "name": "your name",
 },
}
```

I'm gonna split everything above up in pieces so you understand what this means.

`{  }` The brackets these are essential in your OBS raw code the always should be at the beginning and the end of your code.

`"request-type": "TheRequestType"` The request type is needed to point out the request your making [available request types](https://github.com/obsproject/obs-websocket/blob/4.x-current/docs/generated/protocol.md#table-of-contents).

`,` a comma at every end of a line except every opening bracket and the last closing bracket is needed.

If your doing a sub branch like `sourceSettings` or `filterSettings` you need to do it like this

```json
"sourceSettings": {
  "color": 4279410288,
  "name": "your name",
  },
  ```

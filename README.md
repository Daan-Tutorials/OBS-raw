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
"color": 4278255360,
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
---

## Now you know how the basics work where gonna make a request that you're probably gonna use.

First you need to do the brackets.

```json
{

}
```

Then you need to add the request type.


```json
{
"request-type": "SetSourceSettings"
}
```

Then you need to know what elements your gonna use with [SetSourceSettings](https://github.com/obsproject/obs-websocket/blob/4.x-current/docs/generated/protocol.md#setsourcesettings) (all info in this link)

Now that you know what you can put it in

```json
{
"request-type": "SetSourceSettings",
"sourceName": "your source name",
"sourceSettings": {
 "": "",
 },
}
```

But to know what source settings exist you need to do GetSourceSettings

```json
"request-type": "GetSourceSettings",
"sourceName": "your source name",
```

Now that we know that for this color source we can change the color/height and width (these things are diffrent depending on the source)

```json
{
"request-type": "SetSourceSettings",
"sourceName": "your source name",
"sourceSettings": {
  "color": 4278190335
  "height": 500
  "width": 200
 },
}
```
color: Needs to be ABGR with the `Pick Color` sub-action you can convert the color to ABGR rather easily, It is a number so it doesn't need ""

height: It is a number so it doesn't need ""

width: It is a number so it doesn't need ""

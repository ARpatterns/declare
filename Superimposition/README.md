# Superimposition

Superimposition aims to cover a detected entity with a virtual object so that the real object is no longer visible.

![screen 1](docs/images/screens.jpg)

## AR Patterns

_Behavior_
* Event: on floor detection
* [Instant Reaction](https://github.com/ARpatterns/catalog/blob/main/behavioral-patterns/instant-reaction.md): Immediate execution of the staging ahead action

_Augmentation_
* [Superimposition](https://github.com/ARpatterns/catalog/blob/main/augmentation-patterns/superimposition.md): presentation of 3D content replacing the detected entity.
  * Placed: on detected object.
  * Aligned: with detected object.

## Diagram

 | on:call |  &rarr; | do:detect:image |
 |---|---|---|
 
> Install image detector 0.29x0.40 &larr; _on:response_  •••  $SERVER/images/JazzIsBack.jpg 👁
> | _on:detect_ | &rarr; | _do:add to AR anchor_ |
> |---|---|---|
> 
>> 'detected.image.flipped' ➕
> 
> | _as:stated_ | _if:`visible('detected.image.flipped') == false`_ | _do:remove_ |
> |---|---|---|
> 
>> 'detected.image.flipped' ❌


## Code

```json
{
  "$schema": "https://service.metason.net/ar/schemas/action.json",
  "items" : [
    {
      "asset" : "$SERVER/images/JazzIsDown.jpg",
      "attributes" : "wxdxh:0.29x0.0x0.4;",
      "id" : "upsidedown.image",
      "isLocked" : false,
      "name" : "Image Panel",
      "subtype" : "Panel",
      "type" : "Spot",
      "vertices" : [
        [
          0,
          -0.2,
          0
        ]
      ]
    },
    {
      "attributes" : "wxdxh:0.29x0.0x0.4;y:-0.2;rx:-90;",
      "children" : "upsidedown.image",
      "id" : "detected.image.flipped",
      "isLocked" : false,
      "name" : "Detected Image",
      "subtype" : "Group",
      "type" : "Geometry",
      "vertices" : [
        [
          0,
          0,
          0
        ],
        [
          0,
          0,
          1
        ]
      ]
    }
  ],
  "tasks" : [
    {
      "dispatch" : "atstart",
      "do" : "skip",
      "state" : "floor"
    },
    {
      "do" : "detect",
      "id" : "detected.image.flipped",
      "height" : "0.40",
      "img" : "$SERVER/images/JazzIsBack.jpg",
      "op" : "say('Jazz is upside down')",
      "width" : "0.29"
    }
  ]
}
```

## Links

* Detailed Docu: [docs/instantStaging.md](docs/instantStaging.md)
* Source Code: [actions/instantStaging.json](actions/instantStaging.json)
## Links
- ARchi VR [Technical Documentation](https://service.metason.net/ar/docu/)

## References

> [!TIP]
> Try out the examples: Open `superImposition.arproject` in [ARchi Composer](https://service.metason.net/ar/docu/#archi-composer) for browsing, editing, and live-injecting the code from your Mac to the [ARchi VR App](https://archi.metason.net) on your iOS device.

- ARchi VR [Technical Documentation](https://service.metason.net/ar/docu/)
- ARchi VR [App](https://archi.metason.net)
- AR Pattern [Diagram](https://github.com/ARpatterns/diagram)
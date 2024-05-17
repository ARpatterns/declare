# actions/supplement.json



## Items 

__1 'info.panel'__ - Panel  🔐
- Spot.Panel
- Poster by the<br>music club <b>Moods</b> <br> <small><br>Zürich (2021)<br></small>
- color:#000000; bgcolor:#FFBB33CC; scale:0.75;x:-0.5;y:0.0;

__2 'info.line'__ - Polylink  🔓
- Route.Polylink
- color:#FFBB33CC;width:0.013;

__3 'detected.image.enhanced'__ - Detected Image  🔓
- Geometry.Group
- wxdxh:0.29x0.0x0.4;
- children: info.panel, info.line



## Tasks 

 | atstart |  &rarr; | do:skip |
 |---|---|---|
> floor detection ⏮
 
 | on:command |  &rarr; | do:detect:image |
 |---|---|---|
 
> Install image detector 0.29x0.40 &larr; _on:response_  •••  $SERVER/images/JazzIsBack.jpg 👁
> | _on:detect_ | &rarr; | _do:add to AR anchor_ |
> |---|---|---|
> 
>> 'detected.image.enhanced' ➕
> 
> | _as:stated_ | _if:`visible('detected.image.enhanced') == false`_ | _do:remove_ |
> |---|---|---|
> 
>> 'detected.image.enhanced' ❌
 


## References 

__Code Refs__

- actions/supplement.json

__Asset Refs__

- _Detector image:_ $SERVER/images/JazzIsBack.jpg

__Project Refs__

- _Project Name:_ supplement
- _Description:_ Enhance detected image with additional info

__Technology Refs__

- _Technical Documentation :_ https://service.metason.net/ar/docu/
- _AR Pattern Diagram :_ https://github.com/ARpatterns/diagram
- _ARchi VR App :_ https://archi.metason.net

# actions/geoLoc.json



## Items 

__1 'overlay.label'__ - Your Location
- Overlay.Label
- color:#000000;bgcolor:#FF9966DD;cx:0;bottom:80;width:130;height:28;



## Tasks 

 | on:command |  &rarr; | do:skip |
 |---|---|---|
> floor detection ⏭
 
 | on:command |  &rarr; | do:add |
 |---|---|---|
> 'overlay.label' ➕
 
 | on:command |  &rarr; | do:setText |
 |---|---|---|
> 'overlay.label': text = join({'Near', location.place, 'in', location.city}, ' ')
 


## References 

__Code Refs__

- actions/geoLoc.json

__Project Refs__

- _Project Name:_ geolocRemark
- _Description:_ Examples of Ahead Staging Pattern

__Technology Refs__

- _Technical Documentation :_ https://service.metason.net/ar/docu/
- _AR Pattern Diagram :_ https://github.com/ARpatterns/diagram
- _ARchi VR App :_ https://archi.metason.net

# Kiri:Moto todo and notes

## `C` cosmetic, `F` functional, `P` performance, `B` bug fix

* `B` client/worker cache invalidated by latest rotation work
* `B` normals possibly inverted on faces in 2D to 3D conversion
* `B` origin bug (Onshape?) when switching modes in 2.5 and 2.6

* `P` duplicate objects should share same slice data unless rotated or scaled
* `P` allow selection to me decimated on demand (context menu?)
* `P` improve decimation speed: omit point conversion or use wasm
* `P` client/worker interface normalization
* `P` explore widget vertex reloading / replacing (Onshape primarily)

* `F` expose grouping feature
* `F` SVG import to 3D part like images
* `F` bundle current profile into exported device

# FDM

* `B` fix adaptive slicing with multi-extruder
* `B` fix support projection/end with grouped parts
* `B` multi-extruder rendering of raft fails to offset the rest of the print
* `B` multi-extruder purge blocks fail to generate properly for rafts
* `B` first layer support speed should be same as shell speed

* `F` test outlining solid projected areas
* `F` slicing controls per user-defined z-region
* `F` control for size of purge block (with 0=disabled)
* `F` polishing and other non-planar work
* `F` gradient infill https://www.youtube.com/watch?v=hq53gsYREHU&feature=emb_logo
* `F` feather sharp tips by reducing extrusion in area of overlap
* `F` first layer segment large flat areas for better fill reliability
* `F` enable purge blocks when quick layers are detected
* `F` option to support interior bridges when 0% infill
* `F` calculate filament use per extruder per print
* `F` apply finish speed to exposed top and underside flat areas
* `F` expand internal supporting flats / solids before projection

* `P` revisit path routing / optimization
* `P` implement infill clipping in wasm
* `P` solid fill the tops of supports for down facing flats
* `P` sparse infill should follow polys between intersect points

# FDM - SLA

# `P` common support area detection (fork new fdm code)
* `P` prioritize supports by length of unsupported span. mandatory when circularity > X
*     or % area of inner to outer poly is high (making it a thin shell)

# FDM - BELT

* `B` multiple parts with one angled against origin "floats" in preview
* `B` re-add progress calls for all work units

# CAM

* `B` tabs are not cut to exact height
* `B` first rough step too far down in certain circumstances?
* `B` trace open polys are not wound consistently
* `B` path routing with tabs sometimes makes no sense
* `B` clicking on a pop-op should pin it until clicked or [esc]
* `B` need to force cut line at synthetic z bottom (midlines, etc)
* `B` non-clear-voids duplicates thru-holes
* `B` failure to go *up* when moving between parts?
* `B` starting export during animation unleashes chaos
* `B` climb vs conventional not fully consistent after refactor
* `B` outside cutting direction in roughing mode inverted

* `F` intelligently turn circle hole pocket clear into spiral down
* `F` trace follow hole that matches endmill should turn into a drill op
* `F` add climb/conventional into each operation
* `F` update analyzer to detect overhangs
* `F` add linear clearing strategy option for roughing / pocket
* `F` adaptive clearing in roughing mode
* `F` extend acute roughing on inside polys to clear small voids
* `F` option to use part / STL coordinate space to determine X,Y origin
* `F` validate muti-part layout and spacing exceeds largest outside tool diameter
* `F` polygon simplification option in tracing (for image derived maps)
* `F` parameterize dropping close points in prep.js. ensure long segments remain straight
* `F` flat and volumetric rendering of paths
* `F` z planar settings visualizations
* `F` convert acute angles to arcs
* `F` lead-in milling
* `F` trapezoidal tabs in Z
* `F` ease-in and ease-out especially on tab cut-out start/stop
* `F` add option to spiral in vs out (optimal tool life) vs mixed (optimal path)
* `F` add support for tapered ball mills
* `F` can animation clear the mesh in areas where the cuts go through the stock?
* `F` support lathe mode / A-axis / rotary
* `F` gcode output option as zip for multiple or flip ops or tool change
* `F` ease-down should be engaged in all descending cutting operations
* `F` entirely user-selectable origin
* `F` maintain several part orientations + op chains in a single profile

* `P` common part pre-analyze to speed up 'slice' and improve shadow (overhangs)
* `P` redo all path route / planning in prepare to account for terrain before camOut
* `P` detect render message backlog and pause or warn?
* `P` allow faster z movements when contouring (not plunging)
* `P` common / faster shadow generator using vertices shared with ledges

# Laser

* `F` add PLT / HP-GL output format (https://en.wikipedia.org/wiki/HP-GL)

# References

* https://www.canva.com/colors/color-wheel/
* http://lcamtuf.coredump.cx/gcnc/full/
* http://wiki.imal.org/howto/cnc-milling-introduction-cutting-tools
* http://www.twak.co.uk/2011/01/degeneracy-in-weighted-straight.html
* http://photon.chrisgraf.de/

# More CNC

* https://www.researchgate.net/publication/250328721_Toolpath_Optimization_on_Automatic_Removal_Uncut_and_Application

# Zip output

* https://users.cs.jmu.edu/buchhofp/forensics/formats/pkzip.html
* https://en.wikipedia.org/wiki/ZIP_(file_format)
* https://stuk.github.io/jszip/

# Meta

* free-space tetrahedron modeler with vertex mating

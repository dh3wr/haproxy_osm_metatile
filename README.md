# haproxy_osm_metatile
HAProxy render server selection based on metatiles

# Description and goal
OSM render servers with renderd and apache always render a 8x8 metatile. When using HAProxy as a loadbalancer between different render backends, it makes sense to direct tile requests inside of a 8x8 metatile to the same server. This is done by defining variables in haproxy.conf such that the x and y tile number are integer divided by 8 and the result in conjunction with the zoom level is used as a key in a sticky table.

As I have not found such a solution on the internet, I provide the config here.

```bash
# Show us all containers (output formatted with Go Template code)
> docker ps -a --format '{{printf `%-16s %-20s %-25s %-19s` .ID .Image .Names .Status}}'

d4f1d17e8edc     made/nginx:latest    settings_nginxlb_1        Up 2 days
f4f2f0b84f46     made/php:7.1         settings_php_1            Up 2 days
976073638a72     memcached:alpine     settings_memcached_1      Up 2 days
9703643282ad     mysql:5.7            settings_mysql_1          Up 2 days
7f2335d4a3b4     85c01a1407cf         xenodochial_darwin        Exited (1) 3 weeks ago
61ae87cf3072     0f3060868478         jovial_montalcini         Exited (2) 3 weeks ago
f32ea9b27cea     3fd9065eaf02         quizzical_hawking         Exited (1) 3 weeks ago
769f1367c0b2     0c48a9a262c9         upbeat_elion              Exited (2) 3 weeks ago
b3215594ef48     dcd78ecbe980         jovial_nightingale        Exited (2) 3 weeks ago
b0821f310e5b     5bec34f4eb7a         jovial_stonebraker        Exited (1) 3 weeks ago
100972240e7a     c96aefb0907a         kind_archimedes           Exited (1) 3 weeks ago
13ef2ffbd757     c96aefb0907a         vigorous_elbakyan         Exited (1) 3 weeks ago
f862dc8ac902     8f2055f0ac99         youthful_kowalevski       Exited (1) 3 weeks ago
c0cd7f076f2d     0874c24da79b         obione_voldemort          Exited (1) 3 weeks ago

# Killing all exited containers
> docker ps -a | grep Exited | awk '{ print $1 }' | xargs -L1 docker rm
7f2335d4a3b4
4a15e281bc42
61ae87cf3072
f32ea9b27cea
769f1367c0b2
b3215594ef48
b0821f310e5b
100972240e7a
13ef2ffbd757
f862dc8ac902
c0cd7f076f2d

# And result after we delete everything.
> docker ps -a --format '{{printf `%-16s %-20s %-25s %-19s` .ID .Image .Names .Status}}'
d4f1d17e8edc     made/nginx:latest    settings_nginxlb_1        Up 2 days
f4f2f0b84f46     made/php:7.1         settings_php_1            Up 2 days
976073638a72     memcached:alpine     settings_memcached_1      Up 2 days
9703643282ad     mysql:5.7            settings_mysql_1          Up 2 days
```

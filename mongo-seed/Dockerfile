FROM mongo:5.0

COPY france-min-outdoor-temperature.json /tmp/france-min-outdoor-temperature.json
COPY france-elevation-offset.json /tmp/france-elevation-offset.json
CMD mongoimport --host mongodb --db vaillant --collection outdoor-temperature --type json --file /tmp/france-min-outdoor-temperature.json --jsonArray && mongoimport --host mongodb --db vaillant --collection offset --type json --file /tmp/france-elevation-offset.json --jsonArray
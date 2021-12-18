# tykports
FreeBSD ports

## Using as overlay in Poudriere

1. Install poudriere-devel (to get overlay support)
2. Add the port tree to poudriere `/usr/local/bin/poudriere ports -c -p tykports -m git -U https://github.com/tykling/tykports`
3. Copy UIDs to main ports tree `sudo cp /usr/local/poudriere/ports/tykports/UIDs /usr/local/poudriere/ports/default/UIDs.tyk`
4. Copy GIDs to main ports tree `sudo cp /usr/local/poudriere/ports/tykports/GIDs /usr/local/poudriere/ports/default/GIDs.tyk`
5. Include UIDs from overlay ports tree in make.conf: `UID_FILES=${PORTSDIR}/UIDs ${PORTSDIR}/UIDs.tyk`
6. Include GIDs from overlay ports tree in make.conf: `GID_FILES=${PORTSDIR}/GIDs ${PORTSDIR}/GIDs.tyk`
7. Add the ports from the overlay you want to build to the portlist
8. Run poudriere with `-O tykports` to use the overlay


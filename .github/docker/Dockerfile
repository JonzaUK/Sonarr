# Test image for the anime season search branches.
#
# Not a distribution image. There is no s6-overlay, no PUID/PGID handling and no
# update mechanism, because this exists only to get the branch onto a server for
# a before/after search timing. Use the LinuxServer or hotio image for anything
# real.
#
# The binaries are built by the workflow and staged into rootfs/<arch> before
# this runs, so there is no compilation here.

FROM mcr.microsoft.com/dotnet/runtime-deps:10.0

ARG TARGETARCH

COPY rootfs/${TARGETARCH}/ /app/

VOLUME ["/config"]
EXPOSE 8989

ENTRYPOINT ["/app/Sonarr", "-nobrowser", "-data=/config"]

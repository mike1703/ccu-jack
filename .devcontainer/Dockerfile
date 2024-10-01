FROM debian:sid

# Optionally, add incoming to sources.list
#RUN echo 'deb http://incoming.debian.org/debian-buildd buildd-unstable main contrib non-free' > /etc/apt/sources.list.d/incoming.list

# Add deb-src to sources.list
RUN find /etc/apt/sources.list* -type f -exec sed -i 'p; s/^deb /deb-src /' '{}' +

# Install developer tools
RUN apt-get update \
 && apt-get install --no-install-recommends -yV \
    build-essential \
    devscripts \
    equivs

RUN apt-get install --no-install-recommends -yV debmake golang git git-buildpackage

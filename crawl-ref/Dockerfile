ARG web_host=crawl.ufetubus.com
ARG crawl_repo=https://github.com/jgolden5/temp_crawl_spicy.git
ARG version

ARG web_path=/usr/www
ARG user_data=/var/crawl
ARG shared_dir=${user_data}/rcs
ARG checkout_dir=/usr/src
ARG crawl_ref=${checkout_dir}/crawl/crawl-ref

# this gcc can be latest, we just pin it to a version for consistency and rebuild speed
#   so if it doesn't work, just update to the latest version and pin it to that
FROM alpine:3.7 as os_base
RUN apk add --no-cache \
    alpine-sdk \
    bash \
    bison \
    flex \
    perl \
    vim 

#    libfreetype6-dev \
#    liblua5.1-0-dev \
#    libncursesw5-dev \
#    libpng-dev \
#    libsdl2-dev \
#    libsdl2-image-dev \
#    libsdl2-mixer-dev \
#    libsqlite3-dev \
#    libz-dev \ 
#    pkg-config \
#    ttf-dejavu-core \
#    advancecomp \
#    pngcrush \
#    && rm -rf /var/lib/apt/lists/*

FROM os_base as build_base

RUN apk add --no-cache \
    freetype-dev \
    libexecinfo-dev \
    libpng-dev \
    ncurses-dev \
    pngcrush \
    sdl2-dev

ARG web_path
ARG shared_dir
ARG checkout_dir
ARG crawl_ref
ARG crawl_repo
ARG version

WORKDIR ${checkout_dir}
#RUN git clone -q "$crawl_repo" -b "$version" crawl
#WORKDIR ${crawl_ref}/source
#RUN git submodule update --init

FROM alpine:latest
MAINTAINER Avi Aryan <avi.aryan123@gmail.com>

# update tar .. --strip-componenets not available in current version
RUN apk --update add --no-cache tar xz

# http://johnvansickle.com/ffmpeg/
RUN wget -O ffmpeg.tar.xz http://johnvansickle.com/ffmpeg/builds/ffmpeg-git-64bit-static.tar.xz \
	&& mkdir -p ffmpeg \
	&& tar -xf ffmpeg.tar.xz -C ffmpeg --strip-components 1 \
	&& rm ffmpeg.tar.xz \
	&& cd ffmpeg \
	&& find . ! -iname ffmpeg -delete

WORKDIR /ffmpeg

CMD ./ffmpeg

libcurl_dir=../lib/libcurl-7.56.0
libcurl_include=${libcurl_dir}/include
libcurl_lib=${libcurl_dir}/lib

jsoncpp_dir=../lib/jsoncpp-1.8.3
jsoncpp_include=${jsoncpp_dir}/include
jsoncpp_src=${jsoncpp_dir}/src

build_jsoncpp:
	mkdir -p ${jsoncpp_dir}/build
	cd ${jsoncpp_dir}/build; \
	cmake ..; make


libwebsockets_dir=../lib/libwebsockets-2.4.0
libwebsockets_include=${libwebsockets_dir}/include
libwebsockets_lib=${libwebsockets_dir}/lib

libbinacpp_dir=../lib/libbinacpp
libbinacpp_include=${libbinacpp_dir}/include
libbinacpp_lib=${libbinacpp_dir}/lib



%: %.cpp build_jsoncpp
	@echo -n "\nMaking $@\n\n\n"
	g++ -I$(libcurl_include) -I$(jsoncpp_include) -I$(libwebsockets_include) -I$(libbinacpp_include) \
	$@.cpp \
	-L$(libcurl_lib) \
	-L$(libwebsockets_lib) \
	-L$(libbinacpp_lib) \
	-L$(jsoncpp_dir)/build \
	-lcurl -ljsoncpp  -lcrypto -lwebsockets -lbinacpp -o $@

	cat run.template.sh  | sed s/%executable%/$@/ > $@.run.sh
	chmod 755 $@.run.sh



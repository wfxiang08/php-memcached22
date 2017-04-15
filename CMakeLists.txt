cmake_minimum_required(VERSION 3.2)
project(php_memcached)

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++11")

# phpize
# ./configure
#
INCLUDE_DIRECTORIES(
    /usr/include/php
    /usr/include/php/TSRM
    /usr/include/php/Zend
    /usr/include/php/ext
    /usr/include/php/ext/date/lib
)
set(SOURCE_FILES
    fastlz/fastlz.c
    fastlz/fastlz.h
    g_fmt.c
    g_fmt.h
    php_libmemcached_compat.c
    php_libmemcached_compat.h
    php_memcached.c
    php_memcached.h
    php_memcached_private.h
    php_memcached_server.c
    php_memcached_server.h
    php_memcached_session.c
    php_memcached_session.h)

add_executable(php_memcached ${SOURCE_FILES})
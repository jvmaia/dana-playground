# run PAL over Main.o and serve PAL api
dnc . && dana pal.rest Main.o

# curl to get configs
curl -X GET http://localhost:8008/meta/get_all_configs

# curl to update config
curl -X POST -d '{"config":"/Users/josh/coding/tcc-jv/testing/primenumbers/Main.o,/Users/josh/coding/tcc-jv/testing/primenumbers/core/Core.o,/Users/josh/coding/tcc-jv/testing/primenumbers/arithmetic/Arith1.o,/Users/josh/Downloads/dana_osx_x86-64_[272]/components/time/Timer.o|0:1:core.Core,0:3:time.Timer,1:2:arithmetic.Arith"}' -H "Content-Type: application/json" http://localhost:8008/meta/set_config
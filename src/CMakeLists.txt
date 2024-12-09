# 当前文件夹下所有文件为 SRC_LIST
#aux_source_directory(. SRC_LIST)

# set(SRC_LIST 
#     mprpcapplication.cc 
#     mprpcconfig.cc 
#     rpcheader.pb.cc 
#     rpcprovider.cc 
#     mprpcchannel.cc
#     mprpccontroller.cc
#     logger.cc
#     zookeeperutil.cc)

file(GLOB SRC_LIST ${CMAKE_CURRENT_SOURCE_DIR}/*.cc)

# 生成静态库
add_library(mprpc ${SRC_LIST})  

target_link_libraries(mprpc muduo_net muduo_base pthread zookeeper_mt)
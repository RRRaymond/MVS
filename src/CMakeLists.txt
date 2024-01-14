# add shared library
cuda_add_library(ACMMP SHARED
        ACMMP.cpp
        ACMMP.cu
        )

# 设置CUDA的编译选项和包含目录
set_target_properties(ACMMP PROPERTIES CUDA_SEPARABLE_COMPILATION ON)
target_include_directories(ACMMP PUBLIC ${CUDA_INCLUDE_DIRS})

# 链接CUDA库
target_link_libraries(ACMMP ${CUDA_LIBRARIES} ${OpenCV_LIBS})
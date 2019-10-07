add_llvm_library(MLIRGPU STATIC
  IR/GPUDialect.cpp
  IR/DialectRegistration.cpp
  Transforms/KernelOutlining.cpp

  ADDITIONAL_HEADER_DIRS
  ${MLIR_MAIN_INCLUDE_DIR}/mlir/Dialect/GPU
)

add_dependencies(MLIRGPU MLIRGPUOpsIncGen)
target_link_libraries(MLIRGPU MLIRIR MLIRLLVMIR MLIRPass MLIRStandardOps LLVMSupport)

add_llvm_library(MLIRGPUtoNVVMTransforms STATIC
  LowerGpuOpsToNVVMOps.cpp
  )
target_link_libraries(MLIRGPUtoNVVMTransforms
  LLVMSupport
  MLIRGPU
  MLIRLLVMIR
  MLIRNVVMIR
  MLIRStandardToLLVM
  MLIRTransforms
  MLIRPass
  )

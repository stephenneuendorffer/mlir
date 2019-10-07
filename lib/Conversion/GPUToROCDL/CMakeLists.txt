add_llvm_library(MLIRGPUtoROCDLTransforms STATIC
  LowerGpuOpsToROCDLOps.cpp
  )
target_link_libraries(MLIRGPUtoROCDLTransforms
  LLVMSupport
  MLIRGPU
  MLIRLLVMIR
  MLIRROCDLIR
  MLIRStandardToLLVM
  MLIRTransforms
  MLIRPass
  )

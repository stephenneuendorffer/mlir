add_llvm_library(MLIRSPIRVTransforms STATIC
  DecorateSPIRVCompositeTypeLayoutPass.cpp
  )

target_link_libraries(MLIRSPIRVTransforms
  MLIRPass
  MLIRSPIRV
  MLIRTransforms
  )

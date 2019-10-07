add_llvm_library(MLIRLLVMIR STATIC
  IR/LLVMDialect.cpp

  ADDITIONAL_HEADER_DIRS
  ${MLIR_MAIN_INCLUDE_DIR}/mlir/Dialect/LLVMIR
  )
add_dependencies(MLIRLLVMIR MLIRLLVMOpsIncGen MLIRLLVMConversionsIncGen LLVMAsmParser LLVMCore LLVMSupport)
target_link_libraries(MLIRLLVMIR MLIRIR LLVMAsmParser LLVMCore LLVMSupport)

add_llvm_library(MLIRNVVMIR STATIC
  IR/NVVMDialect.cpp

  ADDITIONAL_HEADER_DIRS
  ${MLIR_MAIN_INCLUDE_DIR}/mlir/Dialect/LLVMIR
  )
add_dependencies(MLIRNVVMIR MLIRNVVMOpsIncGen MLIRNVVMConversionsIncGen)
target_link_libraries(MLIRNVVMIR MLIRLLVMIR MLIRIR LLVMAsmParser LLVMCore LLVMSupport)

add_llvm_library(MLIRROCDLIR STATIC
  IR/ROCDLDialect.cpp

  ADDITIONAL_HEADER_DIRS
  ${MLIR_MAIN_INCLUDE_DIR}/mlir/Dialect/LLVMIR
  )
add_dependencies(MLIRROCDLIR MLIRROCDLOpsIncGen MLIRROCDLConversionsIncGen)
target_link_libraries(MLIRROCDLIR MLIRLLVMIR MLIRIR LLVMAsmParser LLVMCore LLVMSupport)

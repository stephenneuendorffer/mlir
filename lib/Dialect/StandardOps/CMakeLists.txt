file(GLOB globbed *.c *.cpp)
add_llvm_library(MLIRStandardOps STATIC
  ${globbed}

  ADDITIONAL_HEADER_DIRS
  ${MLIR_MAIN_INCLUDE_DIR}/mlir/Dialect/StandardOps
  )

add_dependencies(MLIRStandardOps
  MLIRCallOpInterfacesIncGen
  MLIRStandardOpsIncGen
  )
target_link_libraries(MLIRStandardOps MLIRIR MLIRParser LLVMSupport)

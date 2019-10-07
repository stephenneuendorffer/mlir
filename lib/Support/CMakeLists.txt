set(LLVM_OPTIONAL_SOURCES
  FileUtilities.cpp
  JitRunner.cpp
  MlirOptMain.cpp
  StorageUniquer.cpp
  ToolUtilities.cpp
  TranslateClParser.cpp
)

add_llvm_library(MLIRSupport STATIC
  FileUtilities.cpp
  StorageUniquer.cpp
  ToolUtilities.cpp

  ADDITIONAL_HEADER_DIRS
  ${MLIR_MAIN_INCLUDE_DIR}/mlir/Support
  )
target_link_libraries(MLIRSupport Threads::Threads LLVMSupport)

add_llvm_library(MLIROptMain STATIC
  MlirOptMain.cpp

  ADDITIONAL_HEADER_DIRS
  ${MLIR_MAIN_INCLUDE_DIR}/mlir/Support
  )
target_link_libraries(MLIROptMain
  MLIRIR
  MLIRParser
  MLIRPass
  LLVMSupport
  MLIRSupport
  )

add_llvm_library(MLIRTranslateClParser STATIC
  TranslateClParser.cpp

  ADDITIONAL_HEADER_DIRS
  ${MLIR_MAIN_INCLUDE_DIR}/mlir/Support
  )
target_link_libraries(MLIRTranslateClParser MLIRTranslation MLIRIR MLIRAnalysis MLIRParser LLVMSupport)

add_llvm_library(MLIRJitRunner STATIC
  JitRunner.cpp
)
target_link_libraries(MLIRJitRunner PRIVATE
  MLIRExecutionEngine
  MLIRIR
  MLIRParser
  MLIRStandardOps
  MLIRTargetLLVMIR
  MLIRTransforms
  MLIRStandardToLLVM
  MLIRSupport
  LLVMCore
  LLVMSupport
)

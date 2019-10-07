set(LLVM_OPTIONAL_SOURCES
  Analysis.cpp
  ConvertToLLVMDialect.cpp
  LoadStoreOps.cpp
  Transforms.cpp
  DialectConstruction.cpp
  TensorOps.cpp
  )

add_llvm_library(Linalg3 STATIC
  Analysis.cpp
  ConvertToLLVMDialect.cpp
  LoadStoreOps.cpp
  Transforms.cpp
  TensorOps.cpp
  )

target_link_libraries(Linalg3
  PUBLIC
    MLIRAffineOps
    MLIRAnalysis
    MLIRLoopToStandard
    MLIRDialect
    MLIREDSC
    MLIRIR
    MLIRLLVMIR
    MLIRParser
    MLIRPass
    MLIRStandardToLLVM
    MLIRTransforms
    Linalg2
    )

add_llvm_library(Linalg3DialectConstruction STATIC
  DialectConstruction.cpp
  )

target_link_libraries(Linalg3DialectConstruction
  PUBLIC Linalg3)

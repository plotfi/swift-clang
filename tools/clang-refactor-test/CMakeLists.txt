set(LLVM_LINK_COMPONENTS
  support
  )

add_clang_executable(clang-refactor-test
  ClangRefactorTest.cpp
  )

if (LLVM_BUILD_STATIC)
  target_link_libraries(clang-refactor-test
    PRIVATE
    libclang_static
  )
else()
  target_link_libraries(clang-refactor-test
    PRIVATE
    libclang
    clangBasic
    clangFrontend
    clangRewrite
    clangTooling
    clangToolingCore
    clangToolingRefactor
  )
endif()

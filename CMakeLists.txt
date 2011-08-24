cmake_minimum_required(VERSION 2.8)
project(WTF)

set(CMAKE_MODULE_PATH "${CMAKE_SOURCE_DIR}/cmake")
set(WTF_DIR "${CMAKE_SOURCE_DIR}/wtf")
set(ICU_DIR "${CMAKE_SOURCE_DIR}/icu")
set(WTF_LIBRARY_NAME wtf)

list(APPEND WTF_INCLUDE_DIRS
  ${CMAKE_SOURCE_DIR}
  ${WTF_DIR}/text
  ${WTF_DIR}/unicode
  ${ICU_DIR}
  )

list(APPEND WTF_SOURCES
  wtf/Assertions.cpp
  wtf/ByteArray.cpp
  wtf/CryptographicallyRandomNumber.cpp
  wtf/CurrentTime.cpp
  wtf/DateMath.cpp
  wtf/dtoa.cpp
  wtf/DecimalNumber.cpp
  wtf/FastMalloc.cpp
  wtf/HashTable.cpp
  wtf/MD5.cpp
  wtf/MainThread.cpp
  wtf/NullPtr.cpp
  wtf/OSRandomSource.cpp
  wtf/PageAllocationAligned.cpp
  wtf/PageBlock.cpp
  wtf/ParallelJobsGeneric.cpp
  wtf/RandomNumber.cpp
  wtf/RefCountedLeakCounter.cpp
  wtf/SHA1.cpp
  wtf/StackBounds.cpp
  wtf/TCSystemAlloc.cpp
  wtf/ThreadingNone.cpp
  wtf/Threading.cpp
  wtf/TypeTraits.cpp
  wtf/WTFThreadData.cpp
  wtf/text/AtomicString.cpp
  wtf/text/CString.cpp
  wtf/text/StringBuilder.cpp
  wtf/text/StringImpl.cpp
  wtf/text/StringStatics.cpp
  wtf/text/WTFString.cpp
  wtf/unicode/CollatorDefault.cpp
  wtf/unicode/icu/CollatorICU.cpp
  wtf/unicode/UTF8.cpp
  )

list(APPEND WTF_HEADERS
  wtf/Alignment.h
  wtf/AlwaysInline.h
  wtf/ASCIICType.h
  wtf/Assertions.h
  wtf/Atomics.h
  wtf/AVLTree.h
  wtf/Bitmap.h
  wtf/BlockStack.h
  wtf/BloomFilter.h
  wtf/brew/RefPtrBrew.h
  wtf/brew/ShellBrew.h
  wtf/brew/SystemMallocBrew.h
  wtf/BumpPointerAllocator.h
  wtf/ByteArray.h
  wtf/chromium/ChromiumThreading.h
  wtf/Compiler.h
  wtf/Complex.h
  wtf/CrossThreadRefCounted.h
  wtf/CryptographicallyRandomNumber.h
  wtf/CurrentTime.h
  wtf/DateMath.h
  wtf/DecimalNumber.h
  wtf/Decoder.h
  wtf/Deque.h
  wtf/DisallowCType.h
  wtf/DoublyLinkedList.h
  wtf/dtoa.h
  wtf/DynamicAnnotations.h
  wtf/Encoder.h
  wtf/ExportMacros.h
  wtf/FastAllocBase.h
  wtf/FastMalloc.h
  wtf/FixedArray.h
  wtf/Forward.h
  wtf/GetPtr.h
  wtf/HashCountedSet.h
  wtf/HashFunctions.h
  wtf/HashIterators.h
  wtf/HashMap.h
  wtf/HashSet.h
  wtf/HashTable.h
  wtf/HashTraits.h
  wtf/HexNumber.h
  wtf/ListHashSet.h
  wtf/ListRefPtr.h
  wtf/Locker.h
  wtf/MainThread.h
  wtf/MallocZoneSupport.h
  wtf/MathExtras.h
  wtf/MD5.h
  wtf/MessageQueue.h
  wtf/Noncopyable.h
  wtf/NonCopyingSort.h
  wtf/NotFound.h
  wtf/NullPtr.h
  wtf/OSAllocator.h
  wtf/OSRandomSource.h
  wtf/OwnArrayPtr.h
  wtf/OwnFastMallocPtr.h
  wtf/OwnPtr.h
  wtf/OwnPtrCommon.h
  wtf/PageAllocation.h
  wtf/PageAllocationAligned.h
  wtf/PageAllocatorSymbian.h
  wtf/PageBlock.h
  wtf/PageReservation.h
  wtf/ParallelJobs.h
  wtf/ParallelJobsGeneric.h
  wtf/ParallelJobsLibdispatch.h
  wtf/ParallelJobsOpenMP.h
  wtf/PassOwnArrayPtr.h
  wtf/PassOwnPtr.h
  wtf/PassRefPtr.h
  wtf/PassTraits.h
  wtf/Platform.h
  wtf/PossiblyNull.h
  wtf/RandomNumber.h
  wtf/RandomNumberSeed.h
  wtf/RefCounted.h
  wtf/RefCountedLeakCounter.h
  wtf/RefPtr.h
  wtf/RefPtrHashMap.h
  wtf/RetainPtr.h
  wtf/SegmentedVector.h
  wtf/SentinelLinkedList.h
  wtf/SHA1.h
  wtf/SinglyLinkedList.h
  wtf/StackBounds.h
  wtf/StaticConstructors.h
  wtf/StdLibExtras.h
  wtf/StringExtras.h
  wtf/StringHasher.h
  wtf/TCPackedCache.h
  wtf/TCPageMap.h
  wtf/TCSpinLock.h
  wtf/TCSystemAlloc.h
  wtf/text/AtomicString.h
  wtf/text/AtomicStringHash.h
  wtf/text/AtomicStringImpl.h
  wtf/text/CString.h
  wtf/text/StringBuffer.h
  wtf/text/StringBuilder.h
  wtf/text/StringConcatenate.h
  wtf/text/StringHash.h
  wtf/text/StringImpl.h
  wtf/text/StringImplBase.h
  wtf/text/StringOperators.h
  wtf/text/TextPosition.h
  wtf/text/WTFString.h
  wtf/ThreadFunctionInvocation.h
  wtf/ThreadIdentifierDataPthreads.h
  wtf/Threading.h
  wtf/ThreadingPrimitives.h
  wtf/ThreadRestrictionVerifier.h
  wtf/ThreadSafeRefCounted.h
  wtf/ThreadSpecific.h
  wtf/TypeTraits.h
  wtf/unicode/brew/UnicodeBrew.h
  wtf/unicode/CharacterNames.h
  wtf/unicode/Collator.h
  wtf/unicode/glib/UnicodeGLib.h
  wtf/unicode/icu/UnicodeIcu.h
  wtf/unicode/qt4/UnicodeQt4.h
  wtf/unicode/ScriptCodesFromICU.h
  wtf/unicode/Unicode.h
  wtf/unicode/UnicodeMacrosFromICU.h
  wtf/unicode/UTF8.h
  wtf/unicode/wince/UnicodeWinCE.h
  wtf/UnusedParam.h
  wtf/ValueCheck.h
  wtf/Vector.h
  wtf/VectorTraits.h
  wtf/VMTags.h
  wtf/wince/FastMallocWinCE.h
  wtf/wince/MemoryManager.h
  wtf/WTFThreadData.h
  )

if (UNIX)
  list(APPEND WTF_SOURCES wtf/OSAllocatorPosix.cpp)
elseif (WIN32)
  list(APPEND WTF_SOURCES wtf/OSAllocatorWin.cpp)
endif ()

if (APPLE)
  list(APPEND WTF_SOURCES wtf/mac/MainThreadMac.mm)
endif ()

option(SINGLE_THREADED "Enable single threaded mode" OFF)

if (SINGLE_THREADED)
  set(ENABLE_SINGLE_THREADED 1)
else ()
  find_package(Threads REQUIRED)
  list(APPEND WTF_SOURCES
    wtf/ThreadingPthreads.cpp
    wtf/ThreadIdentifierDataPthreads.cpp 
    )
  list(APPEND WTF_LIBRARIES ${CMAKE_THREAD_LIBS_INIT})
  set(HAVE_PTHREADS 1)
endif ()

find_package(ICU REQUIRED)

configure_file(cmakeconfig.h.cmake ${CMAKE_SOURCE_DIR}/cmakeconfig.h)
add_library(${WTF_LIBRARY_NAME} ${ICU_SOURCES} ${WTF_SOURCES})
include_directories(${WTF_LIBRARY_NAME} ${WTF_INCLUDE_DIRS})
target_link_libraries(${WTF_LIBRARY_NAME} ${WTF_LIBRARIES})

install(FILES ${WTF_HEADERS}
  DESTINATION include/wtf
  )
install(TARGETS ${WTF_LIBRARY_NAME}
  LIBRARY DESTINATION lib
  ARCHIVE DESTINATION lib
  )
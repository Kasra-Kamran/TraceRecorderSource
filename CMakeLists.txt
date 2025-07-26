set(SOURCES
    trcAssert.c
    trcCounter.c
    trcDependency.c
    trcDiagnostics.c
    trcEntryTable.c
    trcError.c
    trcEvent.c
    trcEventBuffer.c
    trcExtension.c
    trcHardwarePort.c
    trcHeap.c
    trcInternalEventBuffer.c
    trcInterval.c
    trcISR.c
    trcMultiCoreEventBuffer.c
    trcObject.c
    trcPrint.c
    trcRunnable.c
    trcSnapshotRecorder.c
    trcStackMonitor.c
    trcStateMachine.c
    trcStaticBuffer.c
    trcStreamingRecorder.c
    trcString.c
    trcTask.c
    trcTimestamp.c
    kernelports/FreeRTOS/trcKernelPort.c
)

add_library(TraceRecorder ${SOURCES})

target_include_directories(TraceRecorder PUBLIC include config kernelports/FreeRTOS/config kernelports/FreeRTOS/include
    ${FREERTOS_CONFIG_FILE_DIRECTORY} ${CMSIS_DEVICE_HEADER_PATH})

target_link_libraries(TraceRecorder PRIVATE stm32h5-cmsis)
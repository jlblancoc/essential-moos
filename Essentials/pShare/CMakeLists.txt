#this builds the pScheduler application
set(EXECNAME pShare)

find_package(MOOS 10.0)

#what files are needed?
SET(SRCS   Share.cpp Listener.cpp Route.cpp ShareHelp.cpp pShareMain.cpp)

include_directories( ${${EXECNAME}_INCLUDE_DIRS} ${MOOS_INCLUDE_DIRS} ${MOOS_DEPEND_INCLUDE_DIRS})
add_executable(${EXECNAME} ${SRCS} )
target_link_libraries(${EXECNAME} ${MOOS_LIBRARIES} ${MOOS_DEPEND_LIBRARIES})

INSTALL(TARGETS ${EXECNAME}
  RUNTIME DESTINATION bin
)

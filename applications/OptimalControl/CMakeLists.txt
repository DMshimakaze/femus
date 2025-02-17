CMAKE_MINIMUM_REQUIRED(VERSION 2.8)
  

unset(OPTCONTROL_FOLDER)
set(OPTCONTROL_FOLDER OptimalControl/)

# MHD Optimal Control
  set(OPT_APPLICATION mhdopt)
  ADD_SUBDIRECTORY(${OPT_APPLICATION}/)
  FILE(MAKE_DIRECTORY ${PROJECT_BINARY_DIR}/applications/${OPTCONTROL_FOLDER}/${OPT_APPLICATION}/input/)
  FILE(MAKE_DIRECTORY ${PROJECT_BINARY_DIR}/applications/${OPTCONTROL_FOLDER}/${OPT_APPLICATION}/output/)
  FILE(COPY ${OPT_APPLICATION}/input/ DESTINATION ${PROJECT_BINARY_DIR}/applications/${OPTCONTROL_FOLDER}/${OPT_APPLICATION}/input/)

# Temperature Optimal Control
  set(OPT_APPLICATION tempopt)
  ADD_SUBDIRECTORY(${OPT_APPLICATION}/)
  FILE(MAKE_DIRECTORY ${PROJECT_BINARY_DIR}/applications/${OPTCONTROL_FOLDER}/${OPT_APPLICATION}/input/)
  FILE(MAKE_DIRECTORY ${PROJECT_BINARY_DIR}/applications/${OPTCONTROL_FOLDER}/${OPT_APPLICATION}/output/)
  FILE(COPY ${OPT_APPLICATION}/input/ DESTINATION ${PROJECT_BINARY_DIR}/applications/${OPTCONTROL_FOLDER}/${OPT_APPLICATION}/input/)

# FE test
  set(OPT_APPLICATION fe_test)
  ADD_SUBDIRECTORY(${OPT_APPLICATION}/)
  FILE(MAKE_DIRECTORY ${PROJECT_BINARY_DIR}/applications/${OPTCONTROL_FOLDER}/${OPT_APPLICATION}/input/)
  FILE(MAKE_DIRECTORY ${PROJECT_BINARY_DIR}/applications/${OPTCONTROL_FOLDER}/${OPT_APPLICATION}/output/)
  FILE(COPY ${OPT_APPLICATION}/input/ DESTINATION ${PROJECT_BINARY_DIR}/applications/${OPTCONTROL_FOLDER}/${OPT_APPLICATION}/input/)

  
  ADD_SUBDIRECTORY(./boundary_control_inequality/)
  ADD_SUBDIRECTORY(./nsopt/)
  ADD_SUBDIRECTORY(./solidopt/)
  ADD_SUBDIRECTORY(./frac_norm/)
  ADD_SUBDIRECTORY(./pddm/)
  ADD_SUBDIRECTORY(./elliptic_nonlin/)
  

#-----------------------------------------------------------------------------
set(MODULE_NAME ScoliosisMonitoring)

#-----------------------------------------------------------------------------
set(MODULE_PYTHON_SCRIPTS
  ${MODULE_NAME}.py
  ${MODULE_NAME}Lib/__init__.py
  ${MODULE_NAME}Lib/ToolsViewer.py
  ${MODULE_NAME}Lib/VolumeRenderingPropertiesMenu.py
  ${MODULE_NAME}Lib/VolumeRenderingViewer.py
  ${MODULE_NAME}Lib/VolumesViewer.py
  )

set(MODULE_PYTHON_RESOURCES
  Resources/Icons/AnnotationPointWithArrow.png
  Resources/Models/Stylus_Example.stl
  Resources/Sounds/critico.wav
  Resources/Sounds/notify.wav
  )

#-----------------------------------------------------------------------------
slicerMacroBuildScriptedModule(
  NAME ${MODULE_NAME}
  SCRIPTS ${MODULE_PYTHON_SCRIPTS}
  RESOURCES ${MODULE_PYTHON_RESOURCES}
  WITH_GENERIC_TESTS
  )

#-----------------------------------------------------------------------------
if(BUILD_TESTING)

  # Register the unittest subclass in the main script as a ctest.
  # Note that the test will also be available at runtime.
  slicer_add_python_unittest(SCRIPT ${MODULE_NAME}.py)

  # Additional build-time testing
  add_subdirectory(Testing)
endif()
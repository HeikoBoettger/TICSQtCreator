cmake_minimum_required(VERSION 3.10)

# Remove when sharing with others.
# list(APPEND CMAKE_PREFIX_PATH "/home/[USER]/Qt6/Tools/QtCreator")

project(TICSQtCreator)

set(CMAKE_AUTOMOC ON)
set(CMAKE_AUTORCC ON)
set(CMAKE_AUTOUIC ON)
set(CMAKE_CXX_STANDARD 17)

find_package(QtCreator REQUIRED COMPONENTS Core)
find_package(QT NAMES Qt6 Qt5 REQUIRED COMPONENTS Widgets)
set(QtX Qt${QT_VERSION_MAJOR})

add_qtc_plugin(TICSQtCreator
  PLUGIN_DEPENDS
    QtCreator::Core
    QtCreator::ProjectExplorer
  DEPENDS
    ${QtX}::Widgets
    QtCreator::ExtensionSystem
    QtCreator::Utils
  SOURCES
    .github/workflows/build_cmake.yml
    .github/workflows/README.md
    README.md
    ticsoutputpane.cpp
    ticsoutputpane.h
    ticsqtcreatorconstants.h
    ticsqtcreator_global.h
    TICSQtCreator.json.in
    ticsqtcreatorplugin.cpp
    ticsqtcreatorplugin.h
)

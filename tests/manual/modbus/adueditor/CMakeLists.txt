# Copyright (C) 2022 The Qt Company Ltd.
# SPDX-License-Identifier: BSD-3-Clause

if(NOT QT_BUILD_STANDALONE_TESTS AND NOT QT_BUILDING_QT)
    cmake_minimum_required(VERSION 3.16)
    project(adueditor LANGUAGES CXX)
    find_package(Qt6BuildInternals REQUIRED COMPONENTS STANDALONE_TEST)
endif()

qt_internal_add_manual_test(adueditor
        GUI
    SOURCES
        interface.ui
        main.cpp
        mainwindow.cpp mainwindow.h
        modbustcpclient.cpp modbustcpclient.h modbustcpclient_p.h
        plaintextedit.h
    LIBRARIES
        Qt::Core
        Qt::CorePrivate
        Qt::Gui
        Qt::Network
        Qt::SerialBus
        Qt::SerialBusPrivate
        Qt::SerialPort
        Qt::Widgets
    ENABLE_AUTOGEN_TOOLS
        uic
)

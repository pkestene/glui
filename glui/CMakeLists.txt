SET(GLUI_SRCS
 # header files, so visual studio will show those in the solution, too:
 ../include/glui/Button.h
../include/glui/CheckBox.h
../include/glui/Column.h
../include/glui/CommandLine.h
../include/glui/Context.h
../include/glui/Control.h
../include/glui/EditText.h
../include/glui/FileBrowser.h
../include/glui/GlutWindow.h
../include/glui/List.h
../include/glui/ListBox.h
../include/glui/Main.h
../include/glui/MouseInteraction.h
../include/glui/Panel.h
../include/glui/RadioButton.h
../include/glui/RadioGroup.h
../include/glui/RollOut.h
../include/glui/Rotation.h
../include/glui/ScrollBar.h
../include/glui/Separator.h
../include/glui/Spinner.h
../include/glui/StaticText.h
../include/glui/TextBox.h
../include/glui/TransferFunction.h
../include/glui/Translation.h
../include/glui/Tree.h
../include/glui/TreePanel.h
../include/glui/glui.h

# source files, to build the lib from
 algebra3.cpp
 arcball.cpp
 glui_add_controls.cpp
 glui_bitmap_img_data.cpp
 glui_bitmaps.cpp
 glui_button.cpp
 glui_checkbox.cpp
 glui_column.cpp
 glui_commandline.cpp
 glui_control.cpp
 glui.cpp
 glui_edittext.cpp
 glui_filebrowser.cpp
 glui_listbox.cpp
 glui_list.cpp
 glui_mouse_iaction.cpp
 glui_node.cpp
 glui_panel.cpp
 glui_radio.cpp
 glui_rollout.cpp
 glui_rotation.cpp
 glui_scrollbar.cpp
 glui_separator.cpp
 glui_spinner.cpp
 glui_statictext.cpp
 glui_string.cpp
 glui_textbox.cpp
 glui_translation.cpp
 glui_tree.cpp
 glui_treepanel.cpp
 glui_window.cpp
 glui_transfer_function.cpp
 quaternion.cpp
 viewmodel.cpp
)
#add_library(glui_obj OBJECT ${GLUI_SRCS})
# we need to enable -fPIC this so that the same object code can be used to
# create static *and* shared libraries without double compilation
#set_property(TARGET glui_obj PROPERTY POSITION_INDEPENDENT_CODE 1)

include_directories("${GLUT_INCLUDE_DIR}")

add_library(glui SHARED ${GLUI_SRCS})
target_link_libraries(glui ${GLUT_LIBRARIES} ${OPENGL_LIBRARIES})
set_property(TARGET glui PROPERTY POSITION_INDEPENDENT_CODE 1)
target_compile_definitions(glui PUBLIC glui_DLL_INTERFACE)

add_library(glui_static STATIC ${GLUI_SRCS})
target_link_libraries(glui_static ${GLUT_LIBRARIES})
set_property(TARGET glui_static PROPERTY POSITION_INDEPENDENT_CODE 1)


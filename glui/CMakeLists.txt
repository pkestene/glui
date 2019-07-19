SET(GLUI_SRCS
 # header files, so visual studio will show those in the solution, too:
 include/GL/glui/Button.h
include/GL/glui/CheckBox.h
include/GL/glui/Column.h
include/GL/glui/CommandLine.h
include/GL/glui/Context.h
include/GL/glui/Control.h
include/GL/glui/EditText.h
include/GL/glui/FileBrowser.h
include/GL/glui/GlutWindow.h
include/GL/glui/List.h
include/GL/glui/ListBox.h
include/GL/glui/Main.h
include/GL/glui/MouseInteraction.h
include/GL/glui/Panel.h
include/GL/glui/RadioButton.h
include/GL/glui/RadioGroup.h
include/GL/glui/RollOut.h
include/GL/glui/Rotation.h
include/GL/glui/ScrollBar.h
include/GL/glui/Separator.h
include/GL/glui/Spinner.h
include/GL/glui/StaticText.h
include/GL/glui/TextBox.h
include/GL/glui/TransferFunction.h
include/GL/glui/Translation.h
include/GL/glui/Tree.h
include/GL/glui/TreePanel.h
include/GL/glui.h

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

add_library(glui_static STATIC ${GLUI_SRCS})
target_link_libraries(glui_static ${GLUT_LIBRARIES})
set_property(TARGET glui_static PROPERTY POSITION_INDEPENDENT_CODE 1)


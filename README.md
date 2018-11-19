


# 1. lll

#======================================
# $END$
#======================================


# 1.1. ll
#-------------------
ll


# 2. licensee


# ##### BEGIN GPL LICENSE BLOCK #####
#
#  This program is free software; you can redistribute it and/or
#  modify it under the terms of the GNU General Public License
#  as published by the Free Software Foundation; either version 2
#  of the License, or (at your option) any later version.
#
#  This program is distributed in the hope that it will be useful,
#  but WITHOUT ANY WARRANTY; without even the implied warranty of
#  MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
#  GNU General Public License for more details.
#
#  You should have received a copy of the GNU General Public License
#  along with this program; if not, write to the Free Software Foundation,
#  Inc., 51 Franklin Street, Fifth Floor, Boston, MA 02110-1301, USA.
#
# ##### END GPL LICENSE BLOCK #####

licensee

# 3. infoo

bl_info = {
    "name": "$NAME$",
    "description": "$NAME1$",
    "author": "lingtalfi",
    "version": (0,0,1),
    "blender": (2,79,0),
    "location": "View3D",
    "warning": "",
    "wiki_url": "",
    "category": "TOOLS",
}



# 4. operatorr

class $class$(bpy.types.Operator):
    bl_idname = 'object.$class$'
    bl_label = "$NAME$"
    bl_options = {'REGISTER'}

    @classmethod
    def poll(cls, context):
        return True

    def execute(self, context):
        $END$
        return {'FINISHED'}





# 5. panell

class $NAME$(bpy.types.Panel):
    bl_idname = "view3d.$NAME$"
    bl_label = "$NAME1$"
    bl_space_type = "VIEW_3D"
    bl_region_type = "TOOLS"
    bl_category = "Test_Code"


    def draw(self, context):
        layout = self.layout
        layout.operator("", text="", icon="BLENDER")
        $END$


# 6. piee

class $NAME$(bpy.types.Menu):
    bl_idname = "view3d.$NAME$"
    bl_label = "$NAME1$"

    def draw(self, context):
        pie = self.layout.menu_pie()
        pie.operator("", text="", icon="BLENDER")
        $END$


# 7. keymapss
addon_keymaps = []
def register_keymaps():
    addon = bpy.context.window_manager.keyconfigs.addon
    km = addon.keymaps.new(name = "3D View", space_type = "VIEW_3D")
    kmi = km.keymap_items.new("$NAME$", type = "P", value = "PRESS")
    addon_keymaps.append(km)

def unregister_keymaps():
    wm = bpy.context.window_manager
    for km in addon_keymaps:
        for kmi in km.keymap_items:
            km.keymap_items.remove(kmi)
        wm.keyconfigs.addon.keymaps.remove(km)
    addon_keymaps.clear()



# 8. registerr

def register():
    bpy.utils.register_module(__name__)

def unregister():
    bpy.utils.register_module(__name__)


if __name__ == "__main__":
    register()


# 9. addonn

import bpy
# ----------------------
# addon by lingtalfi
# ----------------------
bl_info = {
    "name": "",
    "description": "",
    "author": "lingtalfi",
    "version": (0, 0, 1),
    "blender": (2, 79, 0),
    "location": "View3D",
    "warning": "",
    "wiki_url": "",
    "category": "TOOLS",
}




class MyOperator(bpy.types.Operator):
    bl_idname = 'object.my_operator'
    bl_label = "MyOperator"
    bl_options = {'REGISTER'}

    @classmethod
    def poll(cls, context):
        return True

    def execute(self, context):
        return {'FINISHED'}



class MyPanel(bpy.types.Panel):
    bl_idname = "view3d.my_panel"
    bl_label = "MyPanel"
    bl_space_type = "VIEW_3D"
    bl_region_type = "TOOLS"
    bl_category = "Test_Code"

    def draw(self, context):
        layout = self.layout
        layout.operator("object.something", text="something", icon="BLENDER")



def register():
    bpy.utils.register_module(__name__)

def unregister():
    bpy.utils.register_module(__name__)


if __name__ == "__main__":
    register()


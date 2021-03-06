cmake_minimum_required(VERSION 3.16)
project(fitd C)

set(CMAKE_C_STANDARD 11)

include_directories(
        src/
        3rdparty/miniz/
)

add_compile_definitions(fitd PRIVATE
        "MINIZ_NO_ARCHIVE_WRITING_APIS"
        "MINIZ_NO_TIME"
        )

add_executable(fitd
        3rdparty/miniz/miniz.c
        3rdparty/miniz/miniz.h

        src/actorList.c
        src/actorList.h
        src/aitdBox.c
        src/aitdBox.h
        src/anim.c
        src/anim.h
        src/animAction.c
        src/animAction.h
        src/common.h
        src/cosTable.c
        src/cosTable.h
        src/debugFont.c
        src/debugFont.h
        src/debugger.c
        src/debugger.h
        src/evalVar.c
        src/evalVar.h
        src/fileAccess.c
        src/fileAccess.h
        src/floor.c
        src/floor.h
        src/fmopl.c
        src/fmopl.h
        src/font.c
        src/font.h
        src/hqr.c
        src/hqr.h
        src/input.c
        src/input.h
        src/inventory.c
        src/inventory.h
        src/life.c
        src/life.h
        src/life_2.c
        src/life_2.h
        src/lifeMacroTable.c
        src/lines.c
        src/main.c
        src/main.h
        src/mainLoop.c
        src/mainLoop.h
        src/music.c
        src/music.h
        src/object.c
        src/object.h
        src/osystem.h
        src/osystemSDL.c
        src/osystemSDL_GL.c
        src/pak.c
        src/pak.h
        src/polys.c
        src/renderer.c
        src/renderer.h
        src/room.c
        src/room.h
        src/save.c
        src/save.h
        src/screen.c
        src/screen.h
        src/sequence.c
        src/startupMenu.c
        src/startupMenu.h
        src/systemMenu.c
        src/systemMenu.h
        src/tatou.c
        src/tatou.h
        src/threadCode.c
        src/threadCode.h
        src/time.c
        src/time.h
        src/track.c
        src/track.h
        src/unpack.c
        src/unpack.h
        src/vars.c
        src/vars.h
        src/version.c
        src/version.h
        src/videoMode.c
        src/videoMode.h
        src/zconf.h
        src/zv.c
        src/zv.h)

set_target_properties(fitd PROPERTIES RUNTIME_OUTPUT_DIRECTORY "${CMAKE_SOURCE_DIR}/release/")

target_link_libraries(fitd opengl32 glu32 SDL2 SDL2_mixer)
if (WIN32)
    target_include_directories(fitd PRIVATE
            3rdparty/sdl2/include/
            3rdparty/sdl2/include/SDL2/
            3rdparty/sdl2_mixer/include/
            3rdparty/sdl2_mixer/include/SDL2/
            )
    target_link_directories(fitd PRIVATE
            3rdparty/sdl2/lib/
            3rdparty/sdl2_mixer/lib/
            )
endif ()

IF(NOT InMMEX)
    MESSAGE(FATAL_ERROR "Use the top-level CMake script!")
ENDIF(NOT InMMEX)

TARGET_SOURCES(LUA PRIVATE
        "${CMAKE_CURRENT_SOURCE_DIR}/lua/src/lapi.c"
        "${CMAKE_CURRENT_SOURCE_DIR}/lua/src/lauxlib.c"
        "${CMAKE_CURRENT_SOURCE_DIR}/lua/src/lbaselib.c"
        "${CMAKE_CURRENT_SOURCE_DIR}/lua/src/lbitlib.c"
        "${CMAKE_CURRENT_SOURCE_DIR}/lua/src/lcode.c"
        "${CMAKE_CURRENT_SOURCE_DIR}/lua/src/lcorolib.c"
        "${CMAKE_CURRENT_SOURCE_DIR}/lua/src/lctype.c"
        "${CMAKE_CURRENT_SOURCE_DIR}/lua/src/ldblib.c"
        "${CMAKE_CURRENT_SOURCE_DIR}/lua/src/ldebug.c"
        "${CMAKE_CURRENT_SOURCE_DIR}/lua/src/ldo.c"
        "${CMAKE_CURRENT_SOURCE_DIR}/lua/src/ldump.c"
        "${CMAKE_CURRENT_SOURCE_DIR}/lua/src/lfunc.c"
        "${CMAKE_CURRENT_SOURCE_DIR}/lua/src/lgc.c"
        "${CMAKE_CURRENT_SOURCE_DIR}/lua/src/linit.c"
        "${CMAKE_CURRENT_SOURCE_DIR}/lua/src/liolib.c"
        "${CMAKE_CURRENT_SOURCE_DIR}/lua/src/llex.c"
        "${CMAKE_CURRENT_SOURCE_DIR}/lua/src/lmathlib.c"
        "${CMAKE_CURRENT_SOURCE_DIR}/lua/src/lmem.c"
        "${CMAKE_CURRENT_SOURCE_DIR}/lua/src/loadlib.c"
        "${CMAKE_CURRENT_SOURCE_DIR}/lua/src/lobject.c"
        "${CMAKE_CURRENT_SOURCE_DIR}/lua/src/lopcodes.c"
        "${CMAKE_CURRENT_SOURCE_DIR}/lua/src/loslib.c"
        "${CMAKE_CURRENT_SOURCE_DIR}/lua/src/lparser.c"
        "${CMAKE_CURRENT_SOURCE_DIR}/lua/src/lstate.c"
        "${CMAKE_CURRENT_SOURCE_DIR}/lua/src/lstring.c"
        "${CMAKE_CURRENT_SOURCE_DIR}/lua/src/lstrlib.c"
        "${CMAKE_CURRENT_SOURCE_DIR}/lua/src/ltable.c"
        "${CMAKE_CURRENT_SOURCE_DIR}/lua/src/ltablib.c"
        "${CMAKE_CURRENT_SOURCE_DIR}/lua/src/ltm.c"
        "${CMAKE_CURRENT_SOURCE_DIR}/lua/src/lua.c"
        "${CMAKE_CURRENT_SOURCE_DIR}/lua/src/luac.c"
        "${CMAKE_CURRENT_SOURCE_DIR}/lua/src/lundump.c"
        "${CMAKE_CURRENT_SOURCE_DIR}/lua/src/lvm.c"
        "${CMAKE_CURRENT_SOURCE_DIR}/lua/src/lzio.c"
        )

TARGET_SOURCES(wxSQLite3 PRIVATE
        "${CMAKE_CURRENT_SOURCE_DIR}/wxsqlite3/src/wxsqlite3.cpp"
        "${CMAKE_CURRENT_SOURCE_DIR}/wxsqlite3/sqlite3/secure/src/sqlite3secure.c"
        )

TARGET_COMPILE_DEFINITIONS(wxSQLite3 PRIVATE
        NOPCH
        SQLITE_CORE
        SQLITE_ENABLE_FTS3
        SQLITE_ENABLE_FTS3_PARENTHESIS
        SQLITE_HAS_CODEC
        SQLITE_ENABLE_EXTFUNC
        SQLITE_ENABLE_COLUMN_METADATA
        SQLITE_ENABLE_JSON1
        HAVE_ACOSH
        HAVE_ASINH
        HAVE_ATANH
        HAVE_ISBLANK
        WXSQLITE3_HAVE_CODEC
        WXSQLITE3_HAVE_METADATA
        WXSQLITE3_USER_AUTHENTICATION
        )

IF(NOT WIN32)
        TARGET_COMPILE_DEFINITIONS(LUA PRIVATE
                LUA_USE_POSIX
                LUA_USE_DLOPEN
                LUA_USE_STRTODHEX
                LUA_USE_AFORMAT
                LUA_USE_LONGLONG
                )
ENDIF()
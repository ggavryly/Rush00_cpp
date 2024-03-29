cmake_minimum_required(VERSION 3.14)
project(Piscine)

set(CMAKE_CXX_STANDARD 98)
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -Wall -Wextra -Werror")
set(SOURCE Rush01/)
# SDL2
set(SDL2_INCLUDE_DIR ~/.brew/Cellar/sdl2/2.0.9_1/include/SDL2/)
set(SDL2_LIBRARY ~/.brew/Cellar/sdl2/2.0.9_1/lib/)
# SDL2 Mixer
set(SDL_MIXER_INCLUDE_DIR ~/.brew/Cellar/sdl2_mixer/2.0.4/include/SDL2/)
set(SDL_MIXER_LIBRARY ~/.brew/Cellar/sdl2_mixer/2.0.4/lib/)
# SDL2 Image
set(SDL_IMAGE_INCLUDE_DIR ~/.brew/Cellar/sdl2_image/2.0.5/include/SDL2/)
set(SDL_IMAGE_LIBRARY ~/.brew/Cellar/sdl2_image/2.0.5/lib/)
# SDL2 TTF
set(SDL_TTF_INCLUDE_DIR ~/.brew/Cellar/sdl2_ttf/2.0.15/include/SDL2/)
set(SDL_TTF_LIBRARY ~/.brew/Cellar/sdl2_ttf/2.0.15/lib/)


set(LIBFT_INCLUDE_DIR ./libft/include/)
set(LIBFT_LIBRARY ./libft/)

set(SOURCE ./src/)
set(INCLUDE ./include/)

include_directories(${SDL2_INCLUDE_DIR}
        ${SDL_MIXER_INCLUDE_DIR}
        ${SDL_IMAGE_INCLUDE_DIR}
        ${SDL_TTF_INCLUDE_DIR}
        ${LIBFT_INCLUDE_DIR}
        ${SOURCE}
        ${INCLUDE})

link_directories(${SDL2_LIBRARY}
        ${SDL_MIXER_LIBRARY}
        ${SDL_IMAGE_LIBRARY}
        ${SDL_TTF_LIBRARY}
        ${LIBFT_LIBRARY}
        ${SOURCE})



file(GLOB all
        "${INCLUDE}*.h"
        "${SOURCE}*.c")


add_executable(doom-nukem   ${all})

target_link_libraries(doom-nukem -O3 -lft -lSDL2 -lSDL2_image -lSDL2_mixer -lSDL2_ttf -lm)

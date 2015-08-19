import os, sys

outputfile = 'sdfont'

env = Environment()
env.Append(CCFLAGS = ['-g3'])
env.Append(LIBS = ['freetype'])
if env['PLATFORM'] == 'darwin':
	env.Append(CPPPATH = ['/opt/local/include/freetype2'])
	env.Append(LIBPATH = ['/opt/local/lib'])
else:
	env.Append(CPPPATH = ['/usr/include/freetype2'])

list = Split("""main.cpp
	stb_image.c
	BinPacker.cpp
	lodepng.cpp
	EncodingHelper.cpp
	""")

list.sort(lambda x, y: cmp(x.lower(),y.lower()))

outputprogram = env.Program(outputfile, list)


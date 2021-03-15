from building import *
import rtconfig

# get current directory
cwd     = GetCurrentDir()

# The set of source files associated with this SConscript file.

src = []
src += Glob('QuEST/src/*.c')
src += Glob('QuEST/src/cpu/QuEST_cpu.c')
src += Glob('QuEST/src/cpu/QuEST_cpu_local.c')

if GetDepend('QUEST_USING_TUTORIAL_EXAMPLE'):
	src += Glob('examples/tutorial_example.c')

if GetDepend('QUEST_USING_DAMPING_EXAMPLE'):
	src += Glob('examples/bernstein_vazirani_circuit.c')

if GetDepend('QUEST_USING_BERNSTEIN_VAZIRANI_CIRCUIT_EXAMPLE'):
	src += Glob('examples/damping_example.c')


LOCAL_CCFLAGS = ''
path    =  [cwd]
path   +=  [cwd + '/QuEST/include']
path   +=  [cwd + '/QuEST/src']
path   +=  [cwd + '/QuEST/src/cpu']

group = DefineGroup('quest', src, CPPPATH = path, depend = ['PKG_USING_QUEST'], LOCAL_CCFLAGS = LOCAL_CCFLAGS)

Return('group')

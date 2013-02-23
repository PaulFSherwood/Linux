
with default.pa
c:\coLinux\pulseaudio-0.9.6>pulseaudio.exe
W: pulsecore/random.c: failed to get proper entropy. Falling back to seeding with current time.
W: pulsecore/core-util.c: secure directory creation not supported on Win32.
W: pulsecore/core.c: failed to allocate shared memory pool. Falling back to a normal memory pool.
E: modules/module-waveout.c: failed to open waveIn
E: pulsecore/module.c: Failed to load  module "module-waveout" (argument: ""): initialization failed.
W: modules/module-detect.c: failed to detect any sound hardware.
E: pulsecore/module.c: Failed to load  module "module-detect" (argument: ""): initialization failed.
E: daemon/main.c: Module load failed.
E: daemon/main.c: failed to initialize daemon.



without default.pa
c:\coLinux\pulseaudio-0.9.6>pulseaudio.exe
W: pulsecore/random.c: failed to get proper entropy. Falling back to seeding with current time.
W: pulsecore/core-util.c: secure directory creation not supported on Win32.
W: pulsecore/core.c: failed to allocate shared memory pool. Falling back to a normal memory pool.
E: daemon/main.c: daemon startup without any loaded modules, refusing to work.

c:\coLinux\pulseaudio-0.9.6>

DIFFERENCE***
E: modules/module-waveout.c: failed to open waveIn
E: pulsecore/module.c: Failed to load  module "module-waveout" (argument: ""): initialization failed.

W: modules/module-detect.c: failed to detect any sound hardware.
E: pulsecore/module.c: Failed to load  module "module-detect" (argument: ""): initialization failed.

E: daemon/main.c: Module load failed.
E: daemon/main.c: failed to initialize daemon.
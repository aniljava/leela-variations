This is the commandline version of Leela. You likely will want to use
this together with a GTP-capable GUI, or some other tool that speaks 
the GTP protocol.

Leela is compatible with GTP version 2, but note that you must add the
"--gtp" option to enable GTP mode.

Allowed options:
  -h [ --help ]                 Show commandline options.
  -g [ --gtp ]                  Enable GTP mode.
  -t [ --threads ] arg (=4)     Number of threads to use.
  -p [ --playouts ] arg         Limit number of playouts.
  -b [ --lagbuffer ] arg (=100) Safety margin for time usage in centiseconds.
  -l [ --logfile ] arg          File to log input/output to.
  -q [ --quiet ]                Disable all diagnostic output.
  --noponder                    Disable pondering.
  --nonets                      Disable use of neural networks.

Note that although the engine can be handicapped by limiting the playout
count, playouts are not standardized so this is not a suitable setting
for comparisons between engines. The OpenCL version is stronger at a
given playout count.

Linux
-----
To get the OpenCL version working, you will have to to install
both the OpenCL libraries for your GPU (e.g. nvidia-libopencl1) as
well as an OpenCL ICD loader (e.g. ocl-icd-libopencl1 or nvidia-opencl-icd
or mesa-opencl-icd - the ICD loader is not card specific and they are 
supposed to be interchangeable).

You can see the installed OpenCL drivers in /etc/OpenCL/vendors/

macOS
-----
You need the boost libraries installed. The recommended way is to
use Homebrew and do a "brew install boost".

Benchmarking
------------
Leela contains a number of internal benchmarks that can be used
to judge the speed (and resulting strength) of a system:

- CPU, integer operations: type "benchmark".

Reference score, Intel Core i5-6600 = ~4600 g/s

- CPU and GPU, floating point: type "netbench". The first result is 
from the GPU (when using OpenCL) or the CPU (regular version), the second 
result is always from the CPU.

Reference score, Intel Core i5-6600 =  ~30 p/s (first/predictions)
Reference score, AMD Radeon R9 390 =  ~602 p/s (first/predictions)
Reference score, NVIDIA GTX 1080 =    ~735 p/s (first/predictions)

Reference score, Intel Core i5-6600 = ~305 p/s (second/evaluations)

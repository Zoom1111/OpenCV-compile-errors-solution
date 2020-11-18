# OpenCV-compile-errors-solution
Some solutions I have met

1. fatal error: boostdesc_bgm.i: no such file or dirctory
a. Download the file `fatal error boostdesc bgm.i pacake.zip` and then unzip it.
b. Copy the files into `opencv_contrib-x.x.x/modules/xfeatures2d/src/`.
c. Finally, you have solved this problem.


2. fatal error: features2d/test/test_detectors_regression.impl.hpp: no such file or dirctory
a. Copy some files in `opencv-x.x.x/modules/features2d/test/` into `opencv_contrib-x.x.x/modules/xfeatures2d/test/`
```
test_descriptors_invariance.impl.hpp
test_descriptors_regression.impl.hpp
test_detectors_invariance.impl.hpp
test_detectors_regression.impl.hpp
test_invariance_utils.hpp
```
b. Chanage the code in `opencv_contrib-x.x.x/modules/xfeatures2d/test/test_features2d.cpp`

```
#include "features2d/test/test_detectors_regression.impl.hpp"
#include "features2d/test/test_descriptors_regression.impl.hpp"
```
change the directory to
```
#include "test_detectors_regression.impl.hpp"
#include "test_descriptors_regression.impl.hpp"
```
c. Chanage the code in `opencv_contrib-x.x.x/modules/xfeatures2d/test/test_rotation_and_scale_invariance.cpp`

```
#include "features2d/test/test_detectors_invariance.impl.hpp" 
#include "features2d/test/test_descriptors_invariance.impl.hpp"
```
change the directory to
```
#include "test_detectors_invariance.impl.hpp"
#include "test_descriptors_invariance.impl.hpp"
```
d. You have solved this problem

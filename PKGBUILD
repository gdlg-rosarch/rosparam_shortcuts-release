# Script generated with Bloom
pkgdesc="ROS - Quickly load variables from rosparam with good command line error checking."
url='https://github.com/davetcoleman/rosparam_shortcuts'

pkgname='ros-lunar-rosparam-shortcuts'
pkgver='0.2.1_1'
pkgrel=1
arch=('any')
license=('BSD'
)

makedepends=('eigen3'
'ros-lunar-catkin'
'ros-lunar-cmake-modules'
'ros-lunar-eigen-conversions'
'ros-lunar-roscpp'
'ros-lunar-roslint'
)

depends=('eigen3'
'ros-lunar-roscpp'
)

conflicts=()
replaces=()

_dir=rosparam_shortcuts
source=()
md5sums=()

prepare() {
    cp -R $startdir/rosparam_shortcuts $srcdir/rosparam_shortcuts
}

build() {
  # Use ROS environment variables
  source /usr/share/ros-build-tools/clear-ros-env.sh
  [ -f /opt/ros/lunar/setup.bash ] && source /opt/ros/lunar/setup.bash

  # Create build directory
  [ -d ${srcdir}/build ] || mkdir ${srcdir}/build
  cd ${srcdir}/build

  # Fix Python2/Python3 conflicts
  /usr/share/ros-build-tools/fix-python-scripts.sh -v 2 ${srcdir}/${_dir}

  # Build project
  cmake ${srcdir}/${_dir} \
        -DCMAKE_BUILD_TYPE=Release \
        -DCATKIN_BUILD_BINARY_PACKAGE=ON \
        -DCMAKE_INSTALL_PREFIX=/opt/ros/lunar \
        -DPYTHON_EXECUTABLE=/usr/bin/python2 \
        -DPYTHON_INCLUDE_DIR=/usr/include/python2.7 \
        -DPYTHON_LIBRARY=/usr/lib/libpython2.7.so \
        -DPYTHON_BASENAME=-python2.7 \
        -DSETUPTOOLS_DEB_LAYOUT=OFF
  make
}

package() {
  cd "${srcdir}/build"
  make DESTDIR="${pkgdir}/" install
}


# Script generated with Bloom
pkgdesc="ROS - Assorted filters designed to operate on 2D planar laser scanners, which use the sensor_msgs/LaserScan type."
url='http://ros.org/wiki/laser_filters'

pkgname='ros-melodic-laser-filters'
pkgver='1.8.6_1'
pkgrel=1
arch=('any')
license=('BSD'
)

makedepends=('ros-melodic-angles'
'ros-melodic-catkin'
'ros-melodic-filters'
'ros-melodic-laser-geometry'
'ros-melodic-message-filters'
'ros-melodic-pluginlib'
'ros-melodic-roscpp'
'ros-melodic-rostest'
'ros-melodic-sensor-msgs'
'ros-melodic-tf'
)

depends=('ros-melodic-angles'
'ros-melodic-filters'
'ros-melodic-laser-geometry'
'ros-melodic-message-filters'
'ros-melodic-pluginlib'
'ros-melodic-roscpp'
'ros-melodic-sensor-msgs'
'ros-melodic-tf'
)

conflicts=()
replaces=()

_dir=laser_filters
source=()
md5sums=()

prepare() {
    cp -R $startdir/laser_filters $srcdir/laser_filters
}

build() {
  # Use ROS environment variables
  source /usr/share/ros-build-tools/clear-ros-env.sh
  [ -f /opt/ros/melodic/setup.bash ] && source /opt/ros/melodic/setup.bash

  # Create build directory
  [ -d ${srcdir}/build ] || mkdir ${srcdir}/build
  cd ${srcdir}/build

  # Fix Python2/Python3 conflicts
  /usr/share/ros-build-tools/fix-python-scripts.sh -v 2 ${srcdir}/${_dir}

  # Build project
  cmake ${srcdir}/${_dir} \
        -DCMAKE_BUILD_TYPE=Release \
        -DCATKIN_BUILD_BINARY_PACKAGE=ON \
        -DCMAKE_INSTALL_PREFIX=/opt/ros/melodic \
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


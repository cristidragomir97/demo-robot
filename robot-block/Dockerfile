FROM balenalib/raspberrypi3-64-debian:buster

RUN install_packages build-essential \
    python3 \
    python3-pip \
    python3-dev \
    python3-setuptools \
    i2c-tools \
    usbutils \
    libboost-math-dev \
    v4l-utils \
    libopus-dev \
    libvpx-dev \
    libsrtp2-dev \
    libopencv-dev \
    libatlas3-base \
    libatlas-base-dev \
    libavcodec-dev \
    libcamera0 \
    libcamera-apps \
    libcamera-tools \
    libcamera-dev \
    libraspberrypi0 \
    libraspberrypi-dev \
    libraspberrypi-doc 
  
# Enable the v4l2 driver for the Raspberry Pi camera
RUN printf "bcm2835-v4l2\n" >> /etc/modules
RUN printf "bcm2835-codec\n" >> /etc/modules
# Set our working directory
WORKDIR /usr/deploy

COPY requirements.txt requirements.txt

# pip install python deps from requirements.txt on the resin.io build server
RUN pip3 install --upgrade pip \
    && pip3 install -r requirements.txt \
    && pip install --extra-index-url https://rospypi.github.io/simple/ rospy \
    && pip install --extra-index-url https://rospypi.github.io/simple/ tf2_ros 

COPY . ./
WORKDIR /usr/deploy/src

RUN chmod +x ./run.sh
CMD ./run.sh

���Ŀǰֻ֧��vs2015���ˣ���Ϊ���������⹷ʺbase�⡣��
���⣬gn��\bootstrap\bootstrap.py �ű���Ҫ�޸Ĳſ�����windows�ϱ��ȥ��
1.������������һ��base��û�е��ļ���ֱ��ɾ���ͺ�
2.��������д��һ��lib���Լ��ӵ��ű��м��ɡ�
3.����is_win�����ٰ�����һЩcc�ļ�����        'base/trace_event/malloc_dump_provider.cc',�Լ�����

�ѵ�google��Ա������windows�ˣ�����


Ϊ���й������������git clone,�ϴ���һ��ѹ���� gn-standalone.7z��ֱ�ӽ�ѹ�ͺ��ˡ�



1.C:\Program Files (x86)\Microsoft Visual Studio 14.0\VC
2.vcvarsall.bat
3.python tools\gn\bootstrap\bootstrap.py -s


�����ǲο���Ϣ

mkdir gn-standalone
cd gn-standalone
mkdir tools
cd tools
git clone https://chromium.googlesource.com/chromium/src/tools/gn
cd ..
mkdir -p third_party/libevent
cd third_party/libevent
wget --no-check-certificate https://chromium.googlesource.com/chromium/chromium/+archive/master/third_party/libevent.tar.gz
tar -xvzf libevent.tar.gz
cd ../..
git clone https://chromium.googlesource.com/chromium/src/base
git clone https://chromium.googlesource.com/chromium/src/build
git clone https://chromium.googlesource.com/chromium/src/build/config
mkdir testing
cd testing
git clone https://chromium.googlesource.com/chromium/testing/gtest
cd ..

# Build
cd tools/gn
./bootstrap/bootstrap.py -s

# At this point, the resulting binary is at:
# gn-standalone/out/Release/gn
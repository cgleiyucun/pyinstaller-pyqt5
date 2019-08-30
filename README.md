＃pyinstaller-pyqt5
使用pyinstaller打包的PyQt5程序后，本机上可以正常运行，
在其他没有python环境电脑下无法运行，报failed to execute script；
首先通过下述方式解决：
a = os.getcwd()
s = r'\PyQt5\Qt\bin'
os.environ['Path'] = os.environ['Path'] + ";" + a + s
把pyqt5的bin目录添加到系统环境变量。
程序更新后，再次出现无法运行的情况
添加此方法后解决
import sys, os
if hasattr(sys, 'frozen'):
    os.environ['PATH'] = sys._MEIPASS + ";" + os.environ['PATH']

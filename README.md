# mobail-apps
from PyQt5.QtWidgets import QApplication, QWidget, QLabel, QLineEdit, QHBoxLayout, QVBoxLayout, QPushButton
from PyQt5.QtCore import Qt
# from instr import *
# иницилизация глобальных переменных
name = ""
age = 7
p1, p2, p3 = 0, 0, 0

win_x, win_y = 200, 100
win_w, win_h = 1000, 600
txt_title = "Тест Руфье"

# 1 экран
class InstrScr(QWidget):
    def __init__(self):
        super().__init__()
        self.initUi()
        self.connects()
        self.set_appear()
        self.show()

    def initUi(self):
        # создание виджетов
        self.lbl_instr = QLabel("Информация...")
        self.lbl_name = QLabel("Введите имя:")
        self.inp_name = QLineEdit()
        self.lbl_age = QLabel("Введите возраст:")
        self.inp_age = QLineEdit("7")
        self.btn = QPushButton("Начать")
        # создание линий
        self.line= QVBoxLayout()
        self.h_line_name = QHBoxLayout()
        self.h_line_age = QHBoxLayout()
        # размещение виджетов на линии
        self.h_line_name.addWidget(self.lbl_name)
        self.h_line_name.addWidget(self.inp_name)
        self.h_line_age.addWidget(self.lbl_age)
        self.h_line_age.addWidget(self.inp_age)
        self.line.addWidget(self.lbl_instr, alignment = Qt.AlignCenter)
        self.line.addLayout(self.h_line_name, )
        self.line.addLayout(self.h_line_age)
        self.line.addWidget(self.btn, alignment = Qt.AlignCenter)
        self.setLayout(self.line)
        

    def connects(self):
        self.btn.clicked.connect(self.next_click)

    def next_click(self):
        self.ps = PulseScr()
        self.hide()

    def set_appear(self):
        self.setWindowTitle(txt_title)
        self.resize(win_w, win_h)
        self.move(win_x, win_y)
# 2 экран
class PulseScr(QWidget):
    def __init__(self):
        super().__init__()
        self.set_appear()
        self.show()

    def set_appear(self):
        self.setWindowTitle(txt_title)
        self.resize(win_w, win_h)
        self.move(win_x, win_y)
# 3 экран
class CheckScr(QWidget):
    def __init__(self):
        super().__init__()
        self.set_appear()
        self.show()

    def set_appear(self):
        self.setWindowTitle(txt_title)
        self.resize(win_w, win_h)
        self.move(win_x, win_y)
# 4 экран
class PulseScr2(QWidget):
    def __init__(self):
        super().__init__()
        self.set_appear()
        self.show()

    def set_appear(self):
        self.setWindowTitle(txt_title)
        self.resize(win_w, win_h)
        self.move(win_x, win_y)
# 5 экран
class ResultScr(QWidget):
    def __init__(self):
        super().__init__()
        self.set_appear()
        self.show()

    def set_appear(self):
        self.setWindowTitle(txt_title)
        self.resize(win_w, win_h)
        self.move(win_x, win_y)

app = QApplication([])
mw = InstrScr()
app.exec_()

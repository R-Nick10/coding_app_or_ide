# code for coding_app_or_ide

# importing needed modules
import sys
from PyQt5 import QtWidgets
from PyQt5.QtWidgets import QDialog, QApplication
from PyQt5.uic import loadUi

# program error class
class Error(QDialog):
    def __init__(self):
        super(Error, self).__init__()
        loadUi('error.ui', self)

# program editor class
class Editor(QDialog):
    def __init__(self):
        super(Editor, self).__init__()
        loadUi('editor.ui', self)
        self.pushButton.clicked.connect(self.play)

    def play(self):
        try:
            print(str(self.plainTextEdit.text()))
        except:
            error = Error()
            widget.addWidget(error)


app = QApplication(sys.argv)
main_win = Editor()

widget = QtWidgets.QStackedWidget()
widget.addWidget(main_win)

widget.show()

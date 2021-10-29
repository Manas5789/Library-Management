# Library-Management
A small sample code to create a Library Management System

import kivy
from kivy.app import App
from kivy.uix.gridlayout import GridLayout
from kivy.uix.label import Label
from kivy.uix.textinput import TextInput
from kivy.uix.button import Button

class LibraryAccounts(GridLayout):
    def __init__(self, **kwargs):
        super(LibraryAccounts, self).__init__()
        self.cols= 4

        self.add_widget(Label(text="Student Name:"))
        self.a_name = TextInput()
        self.add_widget(self.a_name)

        self.add_widget(Label(text=" Book Name:"))
        self.a_book = TextInput()
        self.add_widget(self.a_book)

        self.add_widget(Label(text="Issue date:"))
        self.a_issue = TextInput()
        self.add_widget(self.a_issue)

        self.add_widget(Label(text="Return date:"))
        self.a_return = TextInput()
        self.add_widget(self.a_return)

        self.add_widget(Label(text="Fine:"))
        self.a_fine = TextInput()
        self.add_widget(self.a_fine)

        self.press = Button(text="Click here to print the details")
        self.press.bind(on_press= self.click_me)
        self.add_widget(self.press)

    def click_me(self, instance):
            print("Name of the student:"+self.a_name.text)
            print("Nof the book:" +self.a_book.text)
            print("Issue Date:" +self.a_issue.text)
            print("Returning Date:"+self.a_return.text)
            print("Fine to be paid:"+self.a_fine.text)

class LibraryApp(App):
    def build(self):
        return LibraryAccounts()

if __name__=='__main__':
    LibraryApp().run()

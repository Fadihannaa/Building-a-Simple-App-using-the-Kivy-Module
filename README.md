# Building-a-Simple-App-using-the-Kivy-Module

from kivy.app import App
from kivy.uix.gridlayout import GridLayout
from kivy.uix.label import Label 
from kivy.uix.image import Image 
from kivy.uix.button import Button
from kivy.uix.textinput import TextInput



class sayhello(App):
    def build(self):
        self.window = GridLayout()
        self.window.cols = 1
        self.window.size_hint = (0.6,0.7)
        self.window.pos_hint = {"center_x" :0.5 , " center y ": 0.5  }
        
        
        
        
        
        
        
        
        
        
#        image widget
        self.window.add_widget(Image(source="logo.png"))
#        Label widget
        self.greeting = Label(
          
        text="What's your name",
        font_size = 18,
        color = "#00FFCE",
        padding_y = (20,20),
        size_hint = (1, 0.5)
        )
        self.window.add_widget(self.greeting)
#        text input widget
        self.user = TextInput(multiline = False)
        self.window.add_widget(self.user)
#        Buttom widget
        self.button = Button(
        text="GREET",
        size_hint = (1,0.5),
        bold = True,
        background_color = '#00FFCE'
        
        )
        self.button.bind(on_press=self.callback)
        self.window.add_widget(self.button)
    
        
    def callback(self, instance):
        self.greeting.text = "hello" + self.user.text + "!"
        
        
        
        
        
        return self.window
        
        
        
if __name__ == "__practice__":
    sayhello().run()
    

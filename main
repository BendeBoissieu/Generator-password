import string
from random import randint, choice
from tkinter import *

def generate_password():
    password_min = 6
    password_max = 12
    all_chars = string.ascii_letters + string.punctuation + string.digits

    password = "".join(choice(all_chars) for x in range(randint(password_min,password_max)))
    password_entry.delete(0, END)
    password_entry.insert(0,password)

# creer la fenetre
window = Tk()
window.title('Password generator')
window.geometry('800x500')
window.minsize(400,400)
window.iconbitmap('babysurfers-black.ico')
window.config(background='#4065A4')

# creer la frame principale
frame = Frame(window,  bg='#4065A4')

# creer une sous boite a la droite de l ecran avec l'element parent frame
right_frame = Frame(frame, bg='#4065A4' )

# creation d'une barre de menu
menu_bar = Menu(window)
# creer un premier menu
file_menu = Menu(menu_bar, tearoff=0)
file_menu.add_command(label="New", command=generate_password)
file_menu.add_command(label="Close", command=window.quit)
menu_bar.add_cascade(label="file", menu=file_menu)

# configurer notre fenetre pour ajouter cette menu bar
window.config(menu=menu_bar)


# creation d'une image
width = 300
height = 300
image = PhotoImage(file='lockpng.png').zoom(35).subsample(32)
canvas = Canvas(frame, width=width, height=height, bg='#4065A4', bd=0, highlightthickness=0)
canvas.create_image(width/2, height/2, image=image)
canvas.grid(row=0, column=0, sticky=W)

# creer un titre
label_title = Label(right_frame, text='Mot de passe', font=('Courrier', 30 ), bg='#4065A4', fg='white')
label_title.pack()

# creer un input/entry
password_entry = Entry(right_frame, font=('Courrier', 30 ), bg='#4065A4', fg='white')
password_entry.pack(pady=25)

# creer un bouton
generate_password_button = Button(right_frame, text='Generate', font=('Courrier', 30 ), bg='#4065A4', fg='white', command=generate_password)
generate_password_button.pack(fill=X)



# on place la sous boite a droite de la boite principale
right_frame.grid(row=0, column=1, sticky=W)

frame.pack(expand=YES)
window.mainloop()

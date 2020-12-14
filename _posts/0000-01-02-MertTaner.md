---
layout : slide
title : "GUI Arayüz Tasarımı - Hatırlatıcı Yapımı"
---

from tkinter import*
from tkcalendar import DateEntry

master = Tk()
canvas = Canvas(master , height=450 , width=750)
canvas.pack()

frame_üst = Frame(master , bg ='#007fff')
frame_üst.place(relx=0.1 , rely=0.1 , relwidth=0.8 , relheight=0.1)

frame_sol_alt = Frame(master , bg ='#007fff')
frame_sol_alt.place(relx=0.1 , rely=0.21 , relwidth=0.23 , relheight=0.5)

frame_sag_alt = Frame(master, bg ='#007fff')
frame_sag_alt.place(relx=0.34 , rely=0.21 , relwidth=0.56 , relheight=0.5)

hatırlatma_tipi_etiketi = Label(frame_üst , bg='#007fff' , text='Hatırlatma Türü :' , font='Verdana 12 bold')
hatırlatma_tipi_etiketi.pack(padx=10 , pady=10 , side= LEFT)

hatırlatma_tipi_opsiyon = StringVar(frame_üst)
hatırlatma_tipi_opsiyon.set('\t')

hatırlatma_tipi_açılır_pencere = OptionMenu(
    frame_üst,
    hatırlatma_tipi_opsiyon,
    'Doğum Günü',
    'Harç Yatırma Günü',
    'Kira Ödemesi'
)
hatırlatma_tipi_açılır_pencere.pack(padx=10 , pady=10 ,side= LEFT)

hatırlatma_tarihi = Label(frame_üst , bg='#007fff' , text='Hatırlatma Tipi :' , font='Verdana 12 bold')
hatırlatma_tarihi.pack(padx=10 , pady=10, side=LEFT)

hatırlatma_tarih_seçme = DateEntry(frame_üst ,widht='12', bg='#007fff' , activebackground='blue' , borderwidht=2 , locale ='de_DE')
hatırlatma_tarih_seçme.pack(padx=10 , pady=10 ,side=LEFT)

hatırlatma_yöntemi = Label(frame_sol_alt , bg='#007fff' , text='Hatırlatma Yöntemi' , font='Verdana 10 bold')
hatırlatma_yöntemi.pack(padx=8 , pady=0.50 , anchor=NW)

var = IntVar()

R1 = Radiobutton(frame_sol_alt , text='Sisteme Kayıt Et' , variable = var, value = 1)
R1.pack(padx=20 , pady=10 , anchor=NW)

R2 = Radiobutton(frame_sol_alt , text='E Posta İle Kayıt Et' , variable = var, value = 2)
R2.pack(padx=20 , pady=10 , anchor=NW)

E1 = Label(frame_sol_alt ,text='Eposta :' , font='Verdana 8')
E1.pack()
E2 = Entry(frame_sol_alt)
E2.pack()

Var1 = IntVar
CV1 = Checkbutton(frame_sol_alt , text='Bir Ay Önce' , variable=Var1 , onvalue = 1, offvalue = 0)
CV1.pack(padx=30 , pady=5 , anchor=NW)

#Var2 = IntVar
#CV2 = Checkbutton(frame_sol_alt , text='Bir Hafta Önce' , variable=Var2 , onvalue = 1, offvalue = 0)
#CV2.pack(padx=30 , pady=5 , anchor=NW)

Var3 = IntVar
CV3 = Checkbutton(frame_sol_alt , text='Bir Gün Önce' , variable=Var3 , onvalue = 1, offvalue = 0)
CV3.pack(padx=30 , pady=5 , anchor=NW)

Label(frame_sag_alt , text='Hatırlatma Mesajı' , font='Verdana 12 bold' , bg='#007fff').pack(padx=10 , pady=10 , anchor=NW)

M1 = Text(frame_sag_alt , width=50 , height=9 , bg='#ffffaa')
M1.pack()


gönder_butonu = Button(frame_sag_alt , text='GÖNDER' ,fg='black')
gönder_butonu.pack(side=BOTTOM , pady=5)




master.mainloop()



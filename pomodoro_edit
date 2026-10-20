import tkinter as tk
min=25
sec=0
notPause=True
def get_work():
    global min,sec
    min=25
    sec=0
    minutes.config(text=f'{min:02d}')
    seconds.config(text=f'{sec:02d}')
    break_work.config(text='Take a break',command=take_break)
    status.config(text='Focus!')
    button.config(text='Start')
def take_break():
    global min,sec
    min=5
    sec=0
    minutes.config(text=f'{min:02d}')
    seconds.config(text=f'{sec:02d}')
    break_work.config(text='Get to Work',command=get_work)
    status.config(text='Break!')
    button.config(text='Start')

def Tpurple():
    frame2.config(bg="#BC6BF9")
    frame3.config(bg="#BC6BF9")
    label2.config(bg="#BC6BF9")
    status.config(bg="#BC6BF9")
    button.config(bg="#8429CF")
    restart.config(bg="#8429CF")
    break_work.config(bg="#8429CF")
def Tred():
    frame2.config(bg="#F0727C")
    frame3.config(bg="#F0727C")
    label2.config(bg="#F0727C")
    status.config(bg="#F0727C")
    button.config(bg="#BE3843")
    restart.config(bg="#BE3843")
    break_work.config(bg="#BE3843")
def Tpink():
    frame2.config(bg="#F2B8C6")
    frame3.config(bg="#F2B8C6")
    label2.config(bg="#F2B8C6")
    status.config(bg="#F2B8C6")
    button.config(bg="#D1589A")
    restart.config(bg="#D1589A")
    break_work.config(bg="#D1589A")
def Tblue():
    frame2.config(bg="#8BBDD9")
    frame3.config(bg="#8BBDD9")
    label2.config(bg="#8BBDD9")
    status.config(bg="#8BBDD9")
    button.config(bg="#418CCD")
    restart.config(bg="#418CCD")
    break_work.config(bg="#418CCD")
def Tgreen():
    frame2.config(bg="#64b47c")
    frame3.config(bg="#64b47c")
    label2.config(bg="#64b47c")
    status.config(bg="#64b47c")
    button.config(bg="#21843F")
    restart.config(bg="#21843F")
    break_work.config(bg="#21843F")
def Tyellow():
    frame2.config(bg="#f3efa1")
    frame3.config(bg="#f3efa1")
    label2.config(bg="#f3efa1")
    status.config(bg="#f3efa1")
    button.config(bg="#cac331")
    restart.config(bg="#cac331")
    break_work.config(bg="#cac331")


def restart_btn():
    global min,sec
    if status['text']=='Focus!':
        min=25
    else:
        min=5
    sec=0
    minutes.config(text=f"{min:02d}")
    seconds.config(text=f"{sec:02d}")
    button.config(text='Start')


    
    
    
def resume():
    global notPause
    notPause=True
    start()
def pause():
    global notPause
    button.configure(text='Resume',command=resume)
    notPause=False
    restart.config(state='normal')
    break_work.config(state='normal')
def start():
    global min,sec
    if notPause:
        button.configure(text='Pause',command=pause)
        restart.config(state='disabled')
        break_work.config(state='disabled')
        if sec==0:
            min-=1
            sec=59
        else:
            sec-=1
        minutes.config(text=f"{min:02d}")
        seconds.config(text=f"{sec:02d}")
        if min==0 and sec==0:
            if status['text']=='Focus!':
                min=5
                sec=0
                status.config(text='Break!')
                break_work.config(text='Get to Work')
            else:
                min=25
                sec=0
                status.config(text='Focus!')
                break_work.config(text='Take a Break')
            minutes.config(text=f"{min:02d}")
            seconds.config(text=f"{sec:02d}")
            start()
        else:
            start_btn()
def start_btn():
    root.after(1000,start)
    

root=tk.Tk()
root.geometry('700x600')
root.minsize(400,250)  
root.title('Pomodoro')

frame1=tk.Frame(root)
frame1.pack(fill='both',expand=True)
frame2=tk.Frame(root,bg='#BC6BF9')
frame2.pack(fill='both',expand=True)
frame3=tk.Frame(root,bg='#BC6BF9')
frame3.pack(fill='both',expand='True')


purple=tk.Button(frame1,bg="#BC6BF9",command=Tpurple)
purple.pack(fill='both',expand='True',padx=0,pady=0,side='left')
red=tk.Button(frame1,bg="#F0727C",command=Tred)
red.pack(fill='both',expand='True',padx=0,pady=0,side='left')
pink=tk.Button(frame1,bg="#F2B8C6",command=Tpink)
pink.pack(fill='both',expand='True',padx=0,pady=0,side='left')
blue=tk.Button(frame1,bg="#8BBDD9",command=Tblue)
blue.pack(fill='both',expand='True',padx=0,pady=0,side='left')
green=tk.Button(frame1,bg="#64b47c",command=Tgreen)
green.pack(fill='both',expand='True',padx=0,pady=0,side='left')
yellow=tk.Button(frame1,bg="#f3efa1",command=Tyellow)
yellow.pack(fill='both',expand='True',padx=0,pady=0,side='left')


frame2.rowconfigure(0,weight=1)
frame2.columnconfigure([0,1,2],weight=1)
minutes=tk.Label(frame2,text='25',bg='white',fg='black',font=('Comic Sans MS',50,'bold'))
label2=tk.Label(frame2,text=':',bg='#BC6BF9',fg='black',font=('Comic Sans MS',50,'bold'))
seconds=tk.Label(frame2,text='00',fg='black',bg='white',font=('Comic Sans MS',50,'bold'))
minutes.grid(row=0,column=0,sticky='nsew',padx=20,pady=20,ipadx=10,ipady=20)
label2.grid(row=0,column=1,sticky='nsew')
seconds.grid(row=0,column=2,sticky='nsew',padx=20,pady=20,ipadx=10,ipady=20)

status=tk.Label(frame3,text='Focus!',bg="#BC6BF9",font=('Comic Sans MS',30,'bold'))
status.pack(fill='both',expand=True,pady=(20,0))
button=tk.Button(frame3,text='Start',command=start_btn,bg="#8429CF",fg='white',font=('Comic Sans MS',20,'bold'))
button.pack(fill='both',expand=True,padx=20,pady=(15,20))
restart=tk.Button(frame3,text='Restart',command=restart_btn,bg='#8429CF',fg='white',font=('Comic Sans MS',20,'bold'))
restart.pack(fill='both',expand=True,padx=20,pady=(15,20))
break_work=tk.Button(frame3,text='Take a break',command=take_break,bg='#8429CF',fg='white',font=('Comic Sans MS',20,'bold'))
break_work.pack(fill='both',expand=True,padx=20,pady=(15,20))

root.mainloop()
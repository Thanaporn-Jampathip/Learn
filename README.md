import tkinter as tk

def age():
    born_month1 = int(month1_input.get())
    born_year1 = int(year1_input.get())
    born_month2 = int(month2_input.get())
    born_year2 = int(year2_input.get())
    born_month = 0
    born_year = 0
    if born_month1 < born_month2:
        born_month = born_month1 - born_month2
        born_month = 12 + born_month
        born_year = born_year2 - born_year1
    elif born_month2 < born_month1:
        born_month = born_month1 - born_month2
        born_month = 12 - born_month
        born_year = born_year2 - born_year1
        born_year = born_year - 1
    output1_label.configure(text=born_year)
    output2_label.configure(text=born_month)
window = tk.Tk()
window.title('Test Python')
window.minsize(width=500, height=500)

title_label = tk.Label(master=window, text='คำนวณอายุ')
title_label.pack(pady=20)

title_label = tk.Label(master=window, text='ใส่เดือนเกิด')
title_label.pack()
month1_input = tk.Entry(master=window)
month1_input.pack(pady=5)
title_label = tk.Label(master=window, text='ใส่ปีเกิด')
title_label.pack()
year1_input = tk.Entry(master=window)
year1_input.pack(pady=5)

title_label = tk.Label(master=window, text='ใส่เดือนปัจจุบัน')
title_label.pack()
month2_input = tk.Entry(master=window)
month2_input.pack(pady=5)
title_label = tk.Label(master=window, text='ใส่ปีปัจจุบัน')
title_label.pack()
year2_input = tk.Entry(master=window)
year2_input.pack(pady=5)

title_label = tk.Label(master=window, text='ตอนนี้อายุ')
title_label.pack()
output1_label = tk.Label(master=window, text='...',)
output1_label.pack()
output2_label = tk.Label(master=window, text='...',)
output2_label.pack()

okay_button = tk.Button(master=window, text='okay', command=age)
okay_button.pack(pady=5)
window.mainloop()

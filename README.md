# Filling using a greedy algorithm

<br />

## 1- The type of Knapsack ( Fractional - I/0)  

<br />

### First file make the filling produce the max value also the content of Knapsack with GUI using Tkinter
### producing the result in real time :+1: :shipit:

<br />


### 1- Fraction method
<br />


![alt text](https://github.com/ahmedazab1235/Knapsack-Greedy-Algorithm-Fractional-and-1-0/blob/main/Screen%20Shot%202021-06-23%20at%209.09.43%20PM.png?raw=true)


<br />


### 2- 1/0 method

<br />


![alt text](https://github.com/ahmedazab1235/Knapsack-Greedy-Algorithm-Fractional-and-1-0/blob/main/Screen%20Shot%202021-06-23%20at%209.10.00%20PM.png?raw=true)


<br />



   from tkinter import *



      window = Tk()

      window.title("Ahmed Essam Azab")

      window.geometry('550x400')

      lbl = Label(window, text="Knapsack using Greedy Algorithm")
      lbl.pack(ipadx=10, ipady=10)

      result = Label(window, text="")
      result.pack(side=BOTTOM)

      result2 = Label(window, text="")
      result2.pack(side=BOTTOM)


      lbl2 = Label(window, text="Enter the values of the {} item(s) in order:").pack(anchor=NW)
      txt = Entry(window,width=25)
      txt.insert(0, "60 100 120")
      txt.focus()
      txt.pack()


      lbl3 = Label(window, text="Enter the positive weights of the {} item(s) in order:").pack(anchor=NW)
      txt2 = Entry(window,width=25)
      txt2.insert(0, "10 20 30")
      txt2.pack()


      lbl4 = Label(window, text="Enter maximum weight:").pack(anchor=NW)
      txt3 = Entry(window,width=25)
      txt3.insert(0, "50")
      txt3.pack()



      def clicked():

        x = txt.get()

        y = txt2.get()

        z = txt3.get()

        value = x.split()
        value = [int(v) for v in value]
        weight = y.split()
        weight = [int(w) for w in weight]
        capacity = int(z)

        max_value, knapsack = fractional_knapsack(value, weight, capacity)

        max_value = 'Max value is ' + str(max_value)

        knapsack = 'knapsack is  ' + str(knapsack)

        result.configure(text=max_value)
        result2.configure(text=knapsack)

      def clicked2():

        x = txt.get()

        y = txt2.get()

        z = txt3.get()

        value = x.split()
        value = [int(v) for v in value]
        weight = y.split()
        weight = [int(w) for w in weight]
        capacity = int(z)

        max_value, knapsack = non_fractional_knapsack(value, weight, capacity)

        max_value = 'Max value is ' + str(max_value)

        knapsack = 'knapsack is  ' + str(knapsack)

        result.configure(text=max_value)
        result2.configure(text=knapsack)

      btn = Button(window, text="fractional", command=clicked,bg="orange", fg="red")

      btn.pack(ipadx=10, ipady=10)

      btn = Button(window, text="1/0", command=clicked2,bg="orange", fg="red")

      btn.pack(ipadx=10, ipady=10)

      window.mainloop()
      




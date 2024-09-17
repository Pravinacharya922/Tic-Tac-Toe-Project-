# Final Project - FinTech (Financial Advising for College Students)
# CS 111, Hayes & Reckinger
# Zaina Khalil & Pravin Acharya

import turtle
import random
import math
import matplotlib.pyplot as plt
import numpy as np


#Function called for turtle on click event "yes" if user would like to proceed using the app.
#Function creates the welcome home screen of the app for users.
#Function takes in x/y coordinates.
def home_screen(x, y):
  yes.hideturtle()
  trial.hideturtle()
  s.bgpic("main.gif")

  global advising
  advising = turtle.Turtle()
  turtle.addshape("advising.gif")
  advising.shape("advising.gif")
  advising.penup()
  advising.goto(-200, -75)

  t.penup()
  t.pencolor("midnight blue")
  t.clear()
  t.goto(0, 200)
  global name
  t.write(
      f"Hello {name}!\nWelcome to the Financial Advising App for College Students!",
      False,
      align='center',
      font=('Helvetica', 24, 'bold'))
  t.hideturtle()


#Function that allows for on key screen event if the user chooses to use the financial app.
def more_info():
  t.penup()
  s.clearscreen()
  s.bgpic("invest.gif")
  t.clear()
  t.write(
      "Please direct your attention to the console!\nAnswer the series of questions.\nThe app will generate a personalized budget plan!",
      False,
      align='center',
      font=('Arial', 18))
  t.hideturtle()
  s.update()


# Function creates a specific budget plan based on the expenses and income of the user.
def create_budget(total_expenses, monthly_earning):
  budget = []
  new_tuition = 0.3 * monthly_earning
  new_housing = 0.4 * monthly_earning
  new_food = 0.1 * monthly_earning
  new_other = 0.15 * monthly_earning
  savings = 0.05 * monthly_earning
  budget.append(new_tuition)
  budget.append(new_housing)
  budget.append(new_food)
  budget.append(new_other)
  budget.append(savings)
  t.pencolor("medium violet red")
  t.clear()
  t.goto(0, 200)

  #exit.onclick(end_screen)
  return budget


def plot_budget():
  budget = create_budget(total_expenses, monthly_earning)
  s.clearscreen()
  s.bgcolor("lavender")
  t.goto(0, -250)
  t.write(
      "According to your earning data, your new suggested plan estimates your tuition cost,\n housing expenses, food cost, other expenses, and savings should be \n $"
      + str(budget[0]) + ", $" + str(budget[1]) + ", $" + str(budget[2]) +
      ", $" + str(budget[3]) + ", and $" + str(budget[4]) + " respectively.",
      False,
      align='center',
      font=('Arial', 15))
  labels = open("labels.txt")
  labels = labels.readlines()
  plt.pie(budget, labels=budget)
  plt.legend(labels)
  plt.show()
  #exit.onclick(end_screen)


#Function draws star graphics with a new background color for the ending screen of the app.
def end_screen(x, y):
  s.clearscreen()
  s.bgcolor("lavender")
  t.pencolor("light coral")
  t.penup()
  t.goto(-25, 200)
  t.pendown()
  t.write("You are not eligible for financial advising.",
          False,
          align='center',
          font=('helvetica', 20))
  t.goto(0, 100)
  t.write(
      "Thank you for using the Financial Advising App for College Students!",
      False,
      align='center',
      font=('helvetica', 18, 'bold'))

  create_star("thistle", -100, -150)
  create_star("dark khaki", -300, 0)
  create_star("seashell", 350, -75)
  create_star("forest green", -320, -150)
  create_star("pale turquoise", 25, -120)
  create_star("azure", 250, -200)
  create_star("light blue", 200, -50)
  create_star("pale violet red", 0, 0)


def create_star(color, x, y):
  t.penup()
  t.goto(x, y)
  t.pendown()
  t.fillcolor(color)
  t.begin_fill()
  for i in range(5):  #Creates a Star
    t.forward(60)
    t.left(145)
  t.end_fill()
  t.penup()


def start_app():
  global name
  global user_name
  global password
  name = input("Name: ")
  user_name = input("Enter your NetID (UIC Email): ")
  password = input("Enter your Password: ")
  return name, user_name, password
  main_app()


def start_screen(x, y):
  s.clearscreen()
  s.setup(1000, 700)  #Screen
  s.bgpic("main.gif") 

  t.speed(5)  #Turtle
  t.clear()
  t.penup()
  t.goto(0, 0)
  t.write("Welcome to the Financial Advising App for College Students!",
          False,
          align='center',
          font=('Times', 23, 'bold'))
  t.hideturtle()


def main_app():
  valid = True  #Assign to Enter While Loop

  while valid == True:

    global name
    global user_name
    global password
    name, user_name, password = start_app()

    global trial
    trial = turtle.Turtle()
    turtle.addshape("trial.gif")
    trial.shape("trial.gif")
    trial.penup()
    trial.goto(-350, -200)

    if user_name[-8:] != "@uic.edu":  #Check Valid Username
      print("Invalid Username. Please try again.")
      t.clear()
      t.write("Invalid Username. Please try again.",
              False,
              align='center',
              font=('Arial', 25, 'bold'))
      trial.onclick(start_screen)
      valid = False
      main_app()

    elif len(password) <= 0:  #Check Valid Password
      print("Invalid Password. Please try again.")
      t.clear()
      t.write("Invalid Password. Please try again.",
              False,
              align='center',
              font=('Arial', 25, 'bold'))
      trial.onclick(start_screen)
      valid = False
      main_app()

    else:
      trial.hideturtle()
      global yes
      yes = turtle.Turtle()
      turtle.addshape("yes.gif")
      yes.shape("yes.gif")
      yes.penup()
      yes.goto(0, 170)
      t.clear()
      t.penup()
      t.goto(0, -65)

      global exit
      exit = turtle.Turtle()
      turtle.addshape("exit.gif")
      exit.shape("exit.gif")
      exit.penup()
      exit.goto(280, -200)
      exit.onclick(end_screen)

      t.goto(0, -80)
      t.write(
          "To customize our financial planning report, please confirm your willingness to \ndisclose your monthly earnings by clicking 'yes'?\nYou may click the exit button to leave the app.\n",
          False,
          align='center',
          font=('Arial', 14))
      t.hideturtle()
      yes.onclick(home_screen)
      t.penup()

      global monthly_earning
      monthly_earning = (input(
          "To customize our financial planning report, please confirm your willingness to disclose your monthly earnings by typing 'yes'? "
      )).lower()
      print("You may click the exit button to leave the app.")
      t.clear()
      t.write(
          "We need some more information to assist you. \nPress the space key to proceed!",
          False,
          align='center',
          font=('Arial', 18))
      s.onkey(more_info, 'space')
      s.listen()

      if monthly_earning == "yes":  #Checks the condition & proceeds forward to collect user data.
        print(
            "Please click on the screen and follow the instructions before answering questions."
        )
        monthly_earning = int(input("Please enter your monthly earnings: $"))

        if monthly_earning < 800 and monthly_earning > 5000:  #Cut-Off Earnings
          print("\nYou are not eligible for financial advising.\n")
          end_screen(0, 0)

        elif monthly_earning > 800:
          print("You are eligible for financial advising.")
          tuition_cost = int(input("What is your monthly tuition cost?: $"))
          housing_cost = int(
              input("How much do you spend on rent and housing per month? $"))
          food_cost = int(
              input(
                  "How much do you spend on food (groceries + eating out) per month? $"
              ))
          other_expenses = int(
              input("Please estimate any additional monthly expenses: $"))
          global total_expenses
          total_expenses = tuition_cost + housing_cost + food_cost + other_expenses
          print("Your monthly expenses is equals to $" + str(total_expenses) +
                ".")
          yes.hideturtle()
          #advising.hideturtle()
          t.pencolor("rebecca purple")
          t.clear()
          t.goto(0, 200)
          t.write("Your monthly expenses is equals to $" +
                  str(total_expenses) + ".",
                  False,
                  align='center',
                  font=("Times", 25, 'bold'))

          if total_expenses >= (0.95 * monthly_earning):  #5% Goes to Savings
            print("Your expenses exceed your income.")
            proceed = (input(
                "I would like to suggest a budget plan for you, type 'yes' to proceed. "
            )).lower()
            if proceed == "yes":
              plot_budget()
            else:
              end_screen(0, 0)
              print(
                  "It seems like you will make your plan on your own. Thanks for using our app!"
              )
          else:
            print(
                "Great job! You have a surplus in your budget. Consider saving or investing the extra money."
            )
            own_plan = []
            own_plan.append(tuition_cost)
            own_plan.append(housing_cost)
            own_plan.append(food_cost)
            own_plan.append(other_expenses)
            #exit.onclick(end_screen)#FIX
            s.clearscreen()
            s.bgcolor("khaki")
            t.pencolor("olive drab")
            t.clear()
            t.goto(0, -250)
            t.write(
                "Based on your current expenses, the plan you have looks like the following:",
                False,
                align='center',
                font=("Arial", 15))
            labels = [
                "Tuition Cost ($)", "Housing Cost ($)", "Food Cost ($)",
                "Other Expenses ($)"
            ]
            plt.pie(own_plan, labels=own_plan)
            plt.legend(labels, loc='upper left')
            plt.show()
        else:
          s.clearscreen()
          s.bgcolor("aquamarine")
          create_star("brown", -300, 50)
          create_star("orchid", 200, 50)
          sad = turtle.Turtle()
          turtle.addshape("sad.gif")
          sad.shape("sad.gif")
          sad.penup()
          sad.goto(0, -50)
          t.goto(0, 200)
          t.write("Invalid Input", False, align='center', font=("Times", 40))
          print("Invalid Input")
          trial = turtle.Turtle()
          turtle.addshape("trial.gif")
          trial.shape("trial.gif")
          trial.penup()
          trial.goto(-350, -200)
          trial.onclick(start_screen)
          #main_loop()

      else:
        print("You are not eligible for financial advising.")
        end_screen(0, 0)

  #main_app()#Restart


#Main Code
if __name__ == '__main__':

  s = turtle.getscreen()  #Screen Set-Up
  turtle.title("Welcome to the Financial Advising App for College Students!"
               )  #Turtle Set-Up
  t = turtle.Turtle()  #Turtle Set-Up
  start_screen(0, 0)
  main_app()
  turtle.done()
  turtle.mainloop()

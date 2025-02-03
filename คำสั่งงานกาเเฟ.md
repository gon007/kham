# WinApp-Coffee-Machine
1. โครงสร้างของคลาส CoffeeMachine
คลาส CoffeeMachine เป็นคลาสที่จำลองเครื่องชงกาแฟ ซึ่งมีคุณสมบัติ (Attributes) และพฤติกรรม (Methods) ดังนี้:

Attributes (ตัวแปรของคลาส)
water: int → ปริมาณน้ำในเครื่อง (กรัม)
coffee: int → ปริมาณผงกาแฟ (กรัม)
chocolate: int → ปริมาณผงช็อกโกแลต (กรัม)
milk: int → ปริมาณนม (กรัม)
Methods (ฟังก์ชันของคลาส)
__init__(self, water, coffee, chocolate, milk)
(Constructor) ใช้สำหรับกำหนดค่าปริมาณของส่วนผสมในเครื่องเมื่อสร้างออบเจ็กต์

check_ingredients(self, drink: str) -> bool
(ตรวจสอบวัตถุดิบ) เช็กว่าส่วนผสมที่เหลืออยู่เพียงพอสำหรับการชงเครื่องดื่มหรือไม่

make_drink(self, drink: str) -> str
(ชงเครื่องดื่ม) ถ้าวัตถุดิบพอ จะลดค่าปริมาณของวัตถุดิบและคืนค่าเป็นสตริงที่บอกว่าเครื่องดื่มถูกสร้างขึ้น

refill(self, water: int, coffee: int, chocolate: int, milk: int)
(เติมวัตถุดิบ) เติมส่วนผสมให้กับเครื่องตามค่าที่กำหนด

Class Diagram
+-----------------+
| CoffeeMachine   |
+-----------------+
| - water: int    |
| - coffee: int   |
| - chocolate: int|
| - milk: int     |
+-----------------+
| + __init__(self, water, coffee, chocolate, milk) |
| + check_ingredients(self, drink: str) -> bool |
| + make_drink(self, drink: str) -> str |
| + refill(self, water: int, coffee: int, chocolate: int, milk: int) |
+-----------------+

code 
class CoffeeMachine:
    def __init__(self, water, coffee, chocolate, milk):
        self.water = water
        self.coffee = coffee
        self.chocolate = chocolate
        self.milk = milk

    def check_ingredients(self, drink):
        recipes = {
            "Black Coffee": {"water": 300, "coffee": 20, "chocolate": 0, "milk": 0},
            "Mocha": {"water": 300, "coffee": 20, "chocolate": 10, "milk": 0},
            "Latte": {"water": 300, "coffee": 20, "chocolate": 0, "milk": 10},
            "Hot Chocolate": {"water": 300, "coffee": 0, "chocolate": 20, "milk": 0},
        }

        if drink not in recipes:
            return False

        required = recipes[drink]
        return (self.water >= required["water"] and
                self.coffee >= required["coffee"] and
                self.chocolate >= required["chocolate"] and
                self.milk >= required["milk"])

    def make_drink(self, drink):
        if not self.check_ingredients(drink):
            return "วัตถุดิบไม่เพียงพอ"

        recipes = {
            "Black Coffee": {"water": 300, "coffee": 20, "chocolate": 0, "milk": 0},
            "Mocha": {"water": 300, "coffee": 20, "chocolate": 10, "milk": 0},
            "Latte": {"water": 300, "coffee": 20, "chocolate": 0, "milk": 10},
            "Hot Chocolate": {"water": 300, "coffee": 0, "chocolate": 20, "milk": 0},
        }

        required = recipes[drink]
        self.water -= required["water"]
        self.coffee -= required["coffee"]
        self.chocolate -= required["chocolate"]
        self.milk -= required["milk"]

        return f"ชง {drink} เสร็จแล้ว!"

    def refill(self, water, coffee, chocolate, milk):
        self.water += water
        self.coffee += coffee
        self.chocolate += chocolate
        self.milk += milk

โค้ดไปใช้ใน UI
เชื่อมต่อ CoffeeMachine เข้ากับ UI คุณอาจใช้ Tkinter หรือ PyQt เช่น:
from tkinter import *

def order_coffee():
    drink = drink_var.get()
    result.set(machine.make_drink(drink))

machine = CoffeeMachine(1000, 100, 50, 50)

root = Tk()
root.title("เครื่องชงกาแฟ")

drink_var = StringVar()
result = StringVar()

Label(root, text="เลือกเครื่องดื่ม").pack()
OptionMenu(root, drink_var, "Black Coffee", "Mocha", "Latte", "Hot Chocolate").pack()

Button(root, text="ชง", command=order_coffee).pack()
Label(root, textvariable=result).pack()

root.mainloop() 
 # Coffee Machine Program

โปรแกรมจำลองเครื่องชงกาแฟ รองรับเครื่องดื่ม 4 ชนิด ได้แก่
- Black Coffee
- Mocha
- Latte
- Hot Chocolate

## Class Diagram
![class_diagram](docs/class_diagram.png)

## วิธีใช้งาน
1. รัน `python main.py`
2. เลือกเครื่องดื่มที่ต้องการ
3. ระบบจะแสดงผลว่าชงสำเร็จหรือไม่

## Dependencies
- Python 3.x
- Tkinter (ถ้ามี UI)
- สรุป
CoffeeMachine ถูกออกแบบให้มีคลาสเดียว ควบคุมการชงและเติมวัตถุดิบ
ใช้หลักการ OOP โดยแยก Attributes และ Methods ให้เหมาะสม
สามารถนำไปต่อยอดกับ GUI ได้
ควรเขียน README.md และเพิ่ม Class Diagram เพื่ออธิบายการทำงานของโค้ด


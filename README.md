sales_data = []
commission_data = []

table_commission = [10, 20, 30, 40]
desk_commission = [20, 30, 40, 50]
chair_commission = [30, 40, 50, 60]

while True:
    salesperson_id = input("Enter salesperson ID or -1 to end: ")
    if salesperson_id == "-1":
        break

    table_sales = float(input("Enter table sales: "))
    desk_sales = float(input("Enter desk sales: "))
    chair_sales = float(input("Enter chair sales: "))

    if chair_sales < 0:
        print("Invalid: Enter valid chair sales")
        continue

    table_com = table_commission[0] if table_sales <= 500 else table_commission[1] if table_sales <= 1000 else table_commission[2] if table_sales <= 1500 else table_commission[3]
    desk_com = desk_commission[0] if desk_sales <= 500 else desk_commission[1] if desk_sales <= 1000 else desk_commission[2] if desk_sales <= 1500 else desk_commission[3]
    chair_com = chair_commission[0] if chair_sales <= 500 else chair_commission[1] if chair_sales <= 1000 else chair_commission[2] if chair_sales <= 1500 else chair_commission[3]

    sales_data.append([salesperson_id, table_sales, desk_sales, chair_sales])
    commission_data.append([salesperson_id, table_com, desk_com, chair_com])

total_table_sales = sum(sales[1] for sales in sales_data)
total_desk_sales = sum(sales[2] for sales in sales_data)
total_chair_sales = sum(sales[3] for sales in sales_data)
total_table_com = sum(commission[1] for commission in commission_data)
total_desk_com = sum(commission[2] for commission in commission_data)
total_chair_com = sum(commission[3] for commission in commission_data)

print("\nSales Table")
print("ID Tables Desks Chairs")
for sales in sales_data:
    print(f"{sales[0]} {sales[1]} {sales[2]} {sales[3]}")
print(f"Total {total_table_sales} {total_desk_sales} {total_chair_sales}")

print("\nCommission Table")
print("ID Tables Desks Chairs")
for commission in commission_data:
    print(f"{commission[0]} {commission[1]} {commission[2]} {commission[3]}")
print(f"Total {total_table_com} {total_desk_com} {total_chair_com}")

print("\nYour Name: [Naheem Davidson]")
print("Your Student Number: [991747344]")

import csv
def main ():
    with open('sales.csv', 'r') as csv_file:
        spreadsheet = csv.DictReader(csv_file)
        print('\n************************')
        print('Welcome to the Sales Spreadsheet!')
        print('Please pick an option from:')
        print('1.Total Sales')
        print('2.Sales listed by month')
        print('3.Month highest/lowest sales')
        print('4.All data by month (sales and expenditure)')
        print('5.Average sales')
        print('6.Profit and Loss')
        print('7.Quit')

        task = input('Input option number:')
        options = ['1','2','3','4','5','6','7']
        if task not in options:
            print ('Try again')
            main ()
        else:
            tasks(task, spreadsheet)

def tasks(task, spreadsheet):
                if task == '1': #total sales
                    sales = []
                    total_sales = 0
                    for row in spreadsheet:
                        sales_number = row['sales']
                        year = row['year']
                        sales.append(sales_number)
                        total_sales = total_sales + int(sales_number)

                    print('The total sales across all months in {} is {}'.format(year, total_sales))
                    main ()

                if task == '2': #sales figures each month
                    for row in spreadsheet:
                        sales_number = row['sales']
                        month_name = row['month']
                        year = row['year']
                        print(month_name.title(), year,'= sales of '+ sales_number)
                    main()

                if task == '3': #month lowest and highest sales

                    sales = []

                    for row in spreadsheet:
                        sales_number = row['sales']
                        month_name = row['month']
                        year = row['year']
                        sales.append(sales_number)
                    lowest_sales = (min(sales))
                    highest_sales = (max(sales))
                    print('The lowest sales rate in {} was {}'.format(year,lowest_sales))
                    print('The highest sales rate in {} was {}'.format(year,highest_sales))
                    main()

                if task == '4': #monthly data
                    month = input('Please type the first three letters of your chosen month')
                    for row in spreadsheet:
                        month_name = row['month']
                        if month_name == month:
                            print(dict(row))
                    main()

                if task == '5': #average sales
                    sales = []
                    total_sales = 0
                    for row in spreadsheet:
                        sales_number = row['sales']
                        year = row['year']
                        sales.append(sales_number)
                        total_sales = total_sales + int(sales_number)
                    average_sales = total_sales/len(sales)
                    print('The average sales over {} were {}'.format(year, int(average_sales)))
                    main()

                if task == '6': #profit
                    for row in spreadsheet:
                        month_name = row['month']
                        sales = row['sales']
                        expenditure = row['expenditure']
                        profit = int(sales) - int(expenditure)
                        if profit > 0:
                            print(month_name.title(), profit, 'profit')
                        else:
                            print(month_name.title(), profit, 'loss')
                    question = input('Would you like to know the annual profit? Y/N')
                    if question == 'Y':
                        spreadsheet = csv.DictReader(open('sales.csv', 'r'))
                        total_sales = 0
                        total_exp = 0
                        sales = []
                        expenditure = []

                        for row in spreadsheet:
                            sales_number = (int(row['sales']))
                            sales.append(sales_number)
                            total_sales = total_sales + int(sales_number)
                            expenditure_value = (int(row['expenditure']))
                            expenditure.append(expenditure_value)
                            total_exp = total_exp + int(expenditure_value)
                        annual_profit = (int(total_sales) - int(total_exp))
                        print('The annual profit was {}'.format(annual_profit))
                        main()
                    else:
                        main()

                if task == '7':  # Quit
                    print ('Goodbye!')
                    quit()

main ()




















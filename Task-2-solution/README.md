# Sample solutions to the tasks

## Task 1 - Print out how many transactions have been made at EVANS CYCLES
```python
import csv
evans_cycle_transactions = 0
with open('data.csv') as data_csv_file:
    csv_reader = csv.reader(data_csv_file)
    for csv_line in csv_reader:
        description = csv_line[2] 
        if description == 'EVANS CYCLES':
            evans_cycle_transactions = evans_cycle_transactions + 1

print("Total transaction at EVANS CYCLES is " + str(evans_cycle_transactions))
```
## Task 2 - What is the total spent at AMAZON in this statement?
```python
import csv
line_number = 1
spent_at_amazon = 0.0
with open('data.csv') as data_csv_file:
    csv_reader = csv.reader(data_csv_file)
    for csv_line in csv_reader:
        if line_number != 1:
            description = csv_line[2]
            if description == 'AMAZON':
                paid_out = float(csv_line[3])
                spent_at_amazon = spent_at_amazon + paid_out
        line_number = line_number + 1

print ("Total spent at AMAZON is " + str(spent_at_amazon))
```
## Task 3 - What is the total spent on the '26 Jan 2018'?
```python
import csv
spent_on_26_jan = 0
with open('data.csv') as data_csv_file:
    csv_reader = csv.reader(data_csv_file)
    for csv_line in csv_reader:
        transaction_date = csv_line[0] 
        if transaction_date == '26 Jan 2018':
            paid_out = float(csv_line[3])
            spent_on_26_jan = spent_on_26_jan + paid_out

print ("Total spent on 26th Jan is " + str(spent_on_26_jan))
```
## Task 4 - What is the total paid in over the last two months?
```python
import csv
line_number = 1
paid_in_total = 0
with open('data.csv') as data_csv_file:
    csv_reader = csv.reader(data_csv_file)
    for csv_line in csv_reader:
        if line_number != 1:
            paid_in = csv_line[4]
            if paid_in != '':
                paid_in_total = paid_in_total + float(paid_in)
        line_number = line_number + 1

print ("Total paid in " + str(paid_in_total))
```
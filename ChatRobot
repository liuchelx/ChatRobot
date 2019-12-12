################################

# Authour: che liu 



import random
import datetime


# Let's start with two list:
yeses = ["yes", "y", "of course", "certainly", "sure"]
noses = ["no", "n", "no way", "of course not", "never"]
greeting = ["hi", "hey", "hello", "nihao"]
byes = ['88', 'zaijian', 'bye', 'bye bye']
name = ['name']
calculate = ['how much','calculate','result']
date = ['date', 'time']
age = ['age','old']
gender = ['boy','girl','gender']
number={ 'zero': 0,'one': 1,'two': 2,'three': 3,'four': 4,'five': 5,'six': 6,'seven': 7,
  'eight': 8,'nine': 9,'ten': 10,'eleven': 11,'twelve': 12,'thirteen': 13,
  'fourteen': 14,'fifteen': 15,'sixteen': 16,'seventeen': 17,'eighteen': 18,
  'nineteen': 19,'twenty': 20,'thirty': 30,'forty': 40,'fifty': 50,'sixty': 60,
  'seventy': 70,'eighty': 80,'ninety': 90,'hundred': 100,'thousand':1000,"million":1000000, "billion":1000000000} 
number_large = {100,1000,1000000,1000000000}
cal_symble = ['product','divide','add','subtract']
transnum_1 = []
transnum_2 = []
user_name = 'sir'
flag = 0
count = -2
sum1 = 0
sum2 = 0
temp_num = 0
key_word = name+ age+gender+date +greeting+calculate
answers = yeses + noses


# we want to accept different expressions 
# yes, YES, yes!!, yes of course, y, certainly yes, sure, ...
while True:
  resp = input("Hi! Do you want to talk to me? ==> ") 
  # no, NO, N, n, no way, ABSOLUTELY NOT, ...
  if resp.lower() in yeses:
    print("I am happy that you want to talk with me")

    while True:
      #ask the questions 
      question = input("""Q: (I will answer yes or no, enter "exit" to end) \n""")

      split = question.split()

      # exit function
      if question == "exit":
        index = random.randint(0, len(byes)-1)
        print(f"Bot:{byes[index]}")
        break
      #check if there is key word
      for i in range(0,len(split)):
        for j in range(0,len(key_word)-1):

          if split[i].lower() == key_word[j]:
            flag =flag + 1
            count =j
            human_name = split[i]
          else:
            flag = flag + 0


      if flag >=1:
        #check name key word
        if 0<=count<=len(name)-1:
          print("My name is chatting bot")
          #ask user's name
          user_name_input = input('what is your name? \n')
          user_name_string = user_name_input.split()
          #store user's name
          for name_count in range(0,len(user_name_string)):
            if user_name_string[name_count] == 'name':
              user_name = user_name_string[name_count+2]
          print('nice to meet you',user_name)

        #check age key word
        elif len(name)-1<count<=len(name)+len(age)-1:
          print("I am 7 days old")

        #check gender key word
        elif len(name)+len(age)-1<count<=len(name)+len(age)+len(gender)-1:
          print("I do not have a gender")

        #check date key word
        elif len(name)+len(age)+len(gender)-1<count<=len(name)+len(age)+len(gender)+len(date)-1:
          time = datetime.datetime.now()
          print(f"Bot:The time is {time}")

        #check greeting key word
        elif len(name)+len(age)+len(gender)+len(date)-1 <count <= len(name)+len(age)+len(gender)+len(date)+len(greeting)-1:
          index = random.randint(0, len(greeting)-1)
          print(f"Bot:{greeting[index]}")

        #check calculate key word
        else:
          for n in range(0,len(split)):
            if split[n].lower() in cal_symble:
              cal_count = n
          #split the number before the operation   
          for num1 in range(0,cal_count):
            if split[num1].lower() in number: 
              transnum_1.append(number[split[num1].lower()])
          #split the number after the operation   
          for num2 in range(cal_count,len(split)):
            if split[num2].lower() in number: 
              transnum_2.append(number[split[num2].lower()])
          #add all the number before calculation 
          for num3 in range(0,len(transnum_1)):
            if transnum_1[num3] in number_large and num3>= 1:
              temp_num_1 = transnum_1[num3-1] * transnum_1[num3]
              transnum_1[num3-1] = 0
              transnum_1[num3] = temp_num_1

          for count_3 in range(0,len(transnum_1)):  
            sum1 = transnum_1[count_3] + sum1
          
          #add all the number after calculation 
          for num4 in range(0,len(transnum_2)):
            if transnum_2[num4] in number_large and num4>= 1:
              temp_num_2 = transnum_2[num4-1] * transnum_2[num4]
              transnum_2[num4-1] = 0
              transnum_2[num4] = temp_num_2

          for count_4 in range(0,len(transnum_2)):  
            sum2 = transnum_2[count_4] + sum2

          #check the operation and do the math
          if split[cal_count] =='product':
            print(sum1,'*',sum2,'=',sum1*sum2)
          elif split[cal_count] =='divide':
            print(sum1,'/',sum2,'=',sum1/sum2)
          elif split[cal_count] =='add':
            print(sum1,'+',sum2,'=',sum1+sum2)
          elif split[cal_count] =='substract':
            print(sum1,'-',sum2,'=',sum1-sum2)

        #reset all
        transnum_1 =[]
        transnum_2 =[]
        cal_count =0
        flag =0
        sum1 =0
        sum2=0
        temp_num =0

      #if no key word  
      elif flag == 0:
        answer = random.randint(0,1)
        if answer == 0:
              # answer no
          index = random.randint(0, len(noses)-1)
          print(f"Bot: {noses[index]}")      
        else:
          # answer yes
          index = random.randint(0, len(yeses)-1)
          print(f"Bot: {yeses[index]}")

  elif resp.lower() in noses:
    index = random.randint(0, len(greeting)-1)
    print(f"Bot: {byes[index]}")
    break

  else:
    print("Please tell me if you are willing to talk to me")

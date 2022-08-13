# -insufficient-amount
# The rides are so popular that the lines never stop. The original usage fee for this ride is price, but if you use the ride for the Nth time, you will be charged N times the original usage fee. Complete the solution function to return how much is less than the amount you currently have when you ride the ride count times. However, if the amount is not insufficient, return 0! 놀이기구는 인기가 매우 많아 줄이 끊이질 않습니다. 이 놀이기구의 원래 이용료는 price원 인데, 놀이기구를 N 번 째 이용한다면 원래 이용료의 N배를 받기로 하였습니다. 놀이기구를 count번 타게 되면 현재 자신이 가지고 있는 금액에서 얼마가 모자라는지를 return 하도록 solution 함수를 완성하세요.단, 금액이 부족하지 않으면 0을 return 해라!
# python
# case 1:
def solution(price, money, count):
    return max(0,price*(count+1)*count//2-money)
# case 2:
def solution(price, money, count):
    # answer = -1
    pay = 0
    for i in range(1, count+1):
        pay += (price * i)
    if money < pay:
        return pay - money
    else:
        return 0
# case 3:
def solution(price, money, count):
    answer=-1
    total=0
    for i in range(1,count+1):
        total+=price*i
        answer=money-total
        if answer<0:
            answer*=-1
        else:
            answer=0
    return answer
        
a=solution(3,20,4)
print(a)
#result--> 10= 3*4-(3+6+9+12)

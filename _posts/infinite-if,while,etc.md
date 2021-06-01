---
layout: single
title: '무한 반복문,다중 반복문'
---
오늘은 무한,다중 반복문 문제를 풀어보았는데 아직 나 혼자서 풀기는 어려운 문제들이라고 생각한다.   
알고리즘이 쉽게 떠오르지 않기 때문에 상당히 어렵다.   

[문제상황]   
DAUM에서는 주기적으로 비밀번호를 변경하여 개인정보를 안전하게 보호하고 있습니다.   
ID는 ‘알파벳+숫자’ 의 조합으로, ‘kyunghee8323’과 같이 만들 수 있습니다.   
새로 변경하려는 비밀번호에서 연속된 3글자가 ID에 들어 있다면 그것은 사용이 허락되지 않습니다.   
위에서 설명한 것과 같이 비밀번호 변경 가능 여부를 체크한 후에 비밀번호를 변경하는 프로그램을 작성하시오.   

~~~python
ID='kyunghee8323'
check=True
PW=input('변경하실 아이디를 입력하십시오:')
for x in range(len(PW)-2):
  if PW[x:x+3] in ID:
    check=False
    break
if check==False: print('중복된 문자가 포함되어 있습니다.')
else: print('비밀번호가 변경되었습니다.')
~~~
이런 문제를 풀어보았고 이거나 다음 문제나 둘다 알고리즘을 생각해내지 못했다.   

[문제상황]   
365 자원봉사포털에서는 4월 3주 도서관에서의 주말 봉사활동지원을 받고 있습니다.   
지원자의 이름과 전화번호를 저장하여 조건에 따라 처리한 후 결과를 출력하는 프로그램을 작성하시오.   
조건   
1 신청기한은 정해져 있다.   
2 신청순서대로 3순위까지만 봉사활동이 확정되며 나머지는 대기자가 된다.   
3 확정자 중에 취소가 발생하면 대기자 명단의 1순위를 확장자로 대체한다.   
4 취소는 확정자 중에서만 발생한다고 가정한다.   
5 다음 데이터를 이용하시오.   
이름 연락처   
김형진 010-1111-2222
한유림 010-3333-4444
양정식 010-5555-6666
조재웅 010-7777-8888
강수진 010-9999-1234
~~~python
Member=[]
Wait=['김형진','한유림','양정식','조재웅','강수진']
while True:
  Q=input('신청,취소,종료:')
  if Q=='신청':
    Name=input('신청자 명을 입력하십시오:')
    NB=input('전화번호를 입력하십시오:')
    Member.append(Name)
    Member.append(NB)
    wait.remove(Name)
    if len(Member)<6:
      continue
    else: print('확정자가 다 찼습니다.')
  elif Q== '취소':
    User=input('취소하실 사용자명을 입력하십시오:')
    NB=input('전화번호를 입력하십시오:')
    if User in Member:
      Member.remove(User)
      Member.remove(NB)
    else: print('확정자명단에 없습니다')
    if len(Member)<6:
      Member.append(wait[0])
  else: break
  #2
  comfirm=[]
wait=[]
while True:
  val=input('(신청:1, 취소:2, 종료:3) ==> ')
  if val=='3': break

  phone=input('phone: ')
  if val=='1':
    name=input('name: ')
    if len(comfirm)<3: confirm.append([name, phone])
    else: wait.append([name, phone])
  else:
   for i in range(len(confirm)):
     if confirm[i][1]==phone:
       print('{}님의 신청을 취소하였습니다.'.format(confirm[i][0]))
       del confirm[i]
    confirm.append(wait[0])
    del wait[0]
    print('{}님이 신청되었습니다.'.format(conform[-1][0]))

  print('신청자: ', confirm)
  print('대기자: ', wait)
~~~
첫 번째 풀이는 내가 직접해본것인데 미완성으로 끝났고
두 번째가 모범적인 알고리즘 이라고 보면된다.   
어느정도 생각했다고 생각했지만 많은것들을 놓치고 있었던 것 같다.   
다음 번에도 이런 문제가 나온다고 하니 열심히 풀어봐야할 것 같다.   

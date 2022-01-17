# Python Confusing Terms



1. if \_\_name\_\_== "\_\_main\_\_" ❓

``` python
# 가정 : mod1.py 파일의 add, sub 함수를 다른 폴더에서 사용하고자 한다. 이럴 경우 if __name__ == "__main__"을 쓰면 된다. 만약 이를 사용하지 않고, 다른 폴더에서 import 할 경우 함수의 결과값이 출력된다.
```

> 다시 말해서, 파이썬 셸이나 다른 파이썬 모듈에서 mod1을 import 할 경우에는 mod1.py의 `__name__` 변수에는 mod1.py의 모듈 이름 값 mod1이 저장된다.

> \# mod1.py  
>
> def add(a, b):    
>
> ​	  return a+b 
>
> def sub(a, b):     
>
> ​      return a-b 
>
> 
>
> if \_\_name\_\_ == "\_\_main\_\_":   
>
>  print(add(1, 4))    
>
>  print(sub(4, 2))



2. \_\_init\_\_ 메서드 ❓

``` python
# FourCal 클래스의 인스턴스 a에 setdata 메서드를 수행하지 않고 add 메서드를 수행하면 "AttributeError: 'FourCal' object has no attribute 'first'" 오류가 발생한다. setdata 메서드를 수행해야 객체 a의 객체변수 first와 second가 생성되기 때문이다.

# 이렇게 객체에 초깃값을 설정해야 할 필요가 있을 때는 setdata와 같은 메서드를 호출하여 초깃값을 설정하기보다는 생성자를 구현하는 것이 안전한 방법이다. 생성자(Constructor)란 객체가 생성될 때 자동으로 호출되는 메서드를 의미한다.

# 파이썬 메서드 이름으로 __init__를 사용하면 이 메서드는 생성자가 된다.

# 출처 : https://wikidocs.net/28#constructor
```





3. Class ❓

`a = FourCal()  `

`FourCal.setdata(a, 4, 2)`

위와 같이 `클래스 이름.메서드` 형태로 호출할 때는 객체 a를 첫 번째 매개변수 self에 꼭 전달해 주어야 한다. 반면에 다음처럼 `객체.메서드` 형태로 호출할 때는 self를 반드시 생략해서 호출해야 한다.

`a = FourCal()`

`a.setdata(4, 2)`





4. 객체와 인스턴스의 차이 ❓

클래스로 만든 객체를 인스턴스라고도 한다. 그렇다면 객체와 인스턴스의 차이는 무엇일까? 이렇게 생각해 보자. a = Cookie() 이렇게 만든 a는 객체이다. 그리고 a 객체는 Cookie의 인스턴스이다. 

즉 인스턴스라는 말은 특정 객체(a)가 어떤 클래스(Cookie)의 객체인지를 관계 위주로 설명할 때 사용한다. 

"a는 인스턴스"보다는 "a는 객체"라는 표현이 어울리며 "a는 Cookie의 객체"보다는 "a는 Cookie의 인스턴스"라는 표현이 훨씬 잘 어울린다.

출처 : https://wikidocs.net/28#_2

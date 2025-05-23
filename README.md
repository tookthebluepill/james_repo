# firstgit

I'm studying how to use GitHub.
I like to solve combinatorial problems as a hobby.

This is a python code created to identify the problem conditions of the extremist combinatorial problem
```from itertools import combinations
from itertools import chain
from tqdm import tqdm

선물의종류=5

선물리스트 = [chr(x) for x in range(65,65+선물의종류)]
선물조합 = [list(combinations(선물리스트, x)) for x in range(1, 1+선물수)]
선물조합 = list(chain(*선물조합))
선물조합 = [set(x) for x in 선물조합]

def 클래스분배검증(ClassA, ClassB):
    for A in ClassA:
        for B in ClassB:
            if len(A&B)==0:
                return False
    return True

for 학생수 in tqdm(range(1,100)):
    for 분배 in combinations(선물조합, 2*학생수): 
        # combinations(선물조합, 2*학생수):
        ClassA = 분배[:학생수]
        ClassB = 분배[학생수:]
        
        if 클래스분배검증(ClassA, ClassB): # 이 분배는 옳다
            print(학생수,ClassA, ClassB)
            print(학생수, "is possible")
            break
```

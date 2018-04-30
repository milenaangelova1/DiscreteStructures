
# Алгоритми за генериране на пермутации и комбинации

## 1. Алгоритъм за генериране на пермутации
## Какво е пермутация?
<p align="justify">
  Нека са дадени n различни елемента 
  a<sub>1</sub>, a<sub>2</sub>, . . . , a<sub>n</sub>. Те могат да бъдат подредени по различни начини. Всяко подреждане
   на елементите a<sub>1</sub>, a<sub>2</sub>, . . . , a<sub>n</sub> се нарича пермутация на n елемента. Броят на всички възможни 
  пермутации от n елемента се бележи с P<sub>n</sub>, където P<sub>n</sub> = n!
</p>

<p align="justify">
<b>Задача 1.</b> Да се напише програма, която да реализира генерирането на пермутации. 
</p>
<p align="justify">
  <b>Вход:</b> n <br>
  <b>Изход:</b> Всички пермутации на {1,2,3, ..., n} в нарастващ лексигорафически ред. <br>
</p>
<pre><code>
  1. procedure generatePermutations(n):
  2. for i := 1 To n Then
  3.    s<sub>i</sub> := i
  4. print s<sub>1</sub>, s<sub>2</sub>, …, s<sub>n</sub>  
  5. for i := 2 To n!
  6. {
  7.     m := n - 1
  8.     while s<sub>m</sub> > s<sub>m+1</sub>
  9.       m := m - 1
  10.    k := n
  11.    while s<sub>m</sub> > s<sub>k</sub>
  12.       k := k - 1
  13.    swap(s<sub>m</sub>, s<sub>k</sub>)
  14.    p := m + 1
  15.    q := n
  16.    while p < q 
  17.    {
  18.      swap(s<sub>p</sub>, s<sub>q</sub>)
  19.      p := p + 1
  20.      q := q – 1
  21.    }
  22.  print s<sub>1</sub>, s<sub>2</sub>, …, s<sub>n</sub>
  23.}
</code></pre>

Намерете кои ще са пермутациите при  n = 3.

## 2. Алгоритъм за генериране на комбинации
## Какво е комбинация?
<p align="justify">
Броят на комбинациите без повторение на n елемента от k-ти клас се означава с <math>C<sub>n</sub><sup>k</sup></math> или C(n,k) и е равен на биномния коефициент n над k:
<math>C<sub>n</sub><sup>k</sup> = n! / k!*(n − k)!</math>
Комбинациите на k елемента от множество с n елемента се отнасят до броя на всички възможни различни групи от по k елемента, които могат да бъдат получени при произволно избиране без повторение.
</p>
<p align="text">
  <b>Задача 2.</b> Да се напише програма, която да реализира генерирането на комбинации. За целта използвайте написаният псевдокод по-долу.
</p>
<p align="text">
  <b>Вход:</b> k, n <br>
  <b>Изход:</b> Всички комбинации от k-ти клас на {1,2,3, ...,n} в нарастващ лексикографичен ред. <br>
</p>
<pre><code>
  1. procedure generateCombinations(n, k):
  2. for i := 1 To k Then
  3.   s<sub>i</sub> := i
  4. print s<sub>1</sub>, s<sub>2</sub>, …, s<sub>k</sub>
  5. for i := 2 to C(n, k) Then
  6. {
  7.    m := k
  8.    max_val := n
  9.    while s<sub>m</sub> = max_val
  10.   {
  11.      m := m - 1
  12.      max_val := max_val - 1
  13.   }
  14.   s<sub>m</sub> := s<sub>m</sub> + 1
  15.   for j := m + 1 To k Then
  16.     s<sub>j</sub> := s<sub>j-1</sub> + 1
  17.   print s<sub>1</sub>, s<sub>2</sub>, …, s<sub>k</sub>
  18. }
</code></pre>

Намерете комбинациите при n = 5  и клас k = 3.
1- Bir listeyi düzleştiren (flatten) fonksiyon yazın. Elemanları birden çok katmanlı listelerden ([[3],2] gibi) oluşabileceği gibi, non-scalar verilerden de oluşabilir. Örnek olarak:

input: [[1,'a',['cat'],2],[[[3]],'dog'],4,5]

output: [1,'a','cat',2,3,'dog',4,5]

## Yazdığım Kod

```
flat_list=[]

def flatten(liste):

    for i in liste:
        if type(i)==list:
            flatten(i)

        else:
            flat_list.append(i)

    return flat_list            

l=[[1,'a',['cat'],2],[[[3]],'dog'],4,5]

print(flatten(l))

```

2- Verilen listenin içindeki elemanları tersine döndüren bir fonksiyon yazın. Eğer listenin içindeki elemanlar da liste içeriyorsa onların elemanlarını da tersine döndürün. Örnek olarak:

input: [[1, 2], [3, 4], [5, 6, 7]]

output: [[[7, 6, 5], [4, 3], [2, 1]]

```
reverse_list=[]

def reverse(liste):

    for i in liste:
        if type(i)==list:
            i.sort()
            i=i[::-1]

        reverse_list.append(i)
    
    return reverse_list

l=[[1, 2], [3, 4], [5, 6, 7]]

r=reverse(l)[::-1]

print(r)

```
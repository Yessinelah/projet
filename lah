def STEM_HaACH(ch, n):
    mylist = []
    remplir_list(mylist, ch)
    
    while len(mylist) % n != 0:
        mylist.append(0)

    stem_list = []
    while len(mylist) != 0:
        stem_list.append(mylist[0:n])
        mylist = mylist[n:]
    
    new_list = stem_list[0]
    stem_list = stem_list[1:]
    for x in range(10):
        new_list = melenge_stem(new_list)
    for item in stem_list:
        # for i in range(len(new_list)):
        #     new_list[i] += item[i] % 100
        new_list = list(map(modilo_100_2_array, new_list, item))

        for x in range(10):
            new_list = melenge_stem(new_list) 

    str_list = list(map(toString, new_list))
    return  "".join(str_list) 

    
def toString(x):
    return str(x)

def melenge_stem(list_item):
    for i in range(len(list_item)):
        if i % 2 != 0:
            list_item[i] += list_item[i-1]
    
    j = 7
    for i in range(len(list_item)):
        s = genearte_premier(j)
        list_item[i] = list_item[i] * s + 1
        j = s + 1

    k = list_item[len(list_item) - 1]
    for i in range(len(list_item)-1, 0, -1):
        list_item[i] = list_item[i-1]
    list_item[0] = k

    list_item = list(map(modilo_100, list_item))
    
    return list_item

def modilo_100(x):
    return x % 100

def modilo_100_2_array(x, y):
    return (x + y) % 100

def genearte_premier(s):
    p = s
    while premier(p) == False:
        p += 1
    return p

def premier(x):
    s = 0
    for i in range(1, x+1):
        if x % i == 0:
            s += 1
    return s == 2

def remplir_list(mylist, ch):
    for i in range(len(ch)):
        mylist.append(ord(ch[i]))

#pgpp
ch = input("donner un chaine pour generer :")
n = int(input("donner n entier :"))
print(STEM_HaACH(ch, n))

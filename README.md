# Lista-8
def ordenador(n_list,m_list):
    tamanho=range(len(m_list+n_list))
    crescente=list(set(n_list+m_list))
    r=[crescente[-(n+1)]for n in tamanho]
    return r
    
    

n_test=[3,2,1]
m_test=[17,8,7,5]
print(ordenador(n_test,m_test))

def compra_esquecida_compulsiva(coisas: list,memoria:int):
    comprei=[]
    lembro=[]
    for i in coisas:
        if i not in lembro:
            comprei.append(i)
            if len(lembro)== memoria:
                lembro.pop(0)
            lembro.append(i)
    return comprei

print(compra_esquecida_compulsiva([1,1,2,3,3,4,5,4,2,1],3))#1,2,3,4,5,2,1

def parentese_valido(frase):
    abertos=0
    for i in frase:
        if abertos<0:#se um parentes foi fechado sem ser aberto
            return "Não é valido"
        if i=="(":
            abertos+=1
        if i==")":
            abertos-=1
    if abertos==0:
        return "É valido"
    else:
        return "Não é valido"

print(parentese_valido(") é pra responder não"))
print(parentese_valido("(( é pra responder não)"))
print(parentese_valido("(é pra (r)esponder sim)"))

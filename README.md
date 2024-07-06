# Lista-8
def ordenador(n_list,m_list):
    tamanho=range(len(m_list+n_list))
    crescente=list(set(n_list+m_list))
    r=[crescente[-(n+1)]for n in tamanho]
    return r
    
    

n_test=[3,2,1]
m_test=[17,8,7,5]
print(ordenador(n_test,m_test))

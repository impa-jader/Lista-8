# Lista-8
Resposta= """Jader Duarte - lista 8- questão 1 
Saida:

""" 
print(Resposta)

def ordenador(n_list,m_list):
    tamanho=len(m_list+n_list)
    n_indice=0
    m_indice=0
    r=[]
    while len(r)<tamanho:
        if n_indice==len(n_list):
            while len(r)<tamanho:
                r.append(m_list[m_indice])
                m_indice+=1
        elif m_indice==len(m_list):
            while len(r)<tamanho:
                r.append(n_list[n_indice])
                n_indice+=1
                    
        elif n_list[n_indice]>m_list[m_indice]:
            r.append(n_list[n_indice])
            n_indice+=1

        elif n_list[n_indice]<m_list[m_indice]:
            r.append(m_list[m_indice])
            m_indice+=1
    return r


    

n_test=[3,2,1]
m_test=[17,8,7,5]
print(ordenador(n_test,m_test))#17,8,7,5,3,2,1

Resposta= """
Jader Duarte - lista 8- questão 2 
Saida:

""" 
print(Resposta)

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

Resposta= """
Jader Duarte - lista 8- questão 3 
Saida:

""" 
print(Resposta)

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

Resposta= """
Jader Duarte - lista 8- questão 2 
Saida:

""" 
print(Resposta)

# mandarei em zip como modulo
class Point2D:
	def __init__(self,x,y):
		self.cord= (x,y)
	
class Polygon:
	def __init__(self,points,color):
		self.points= points	
		self.color=color
			
class polygons:
        def __init__(self):
            self.lista = {}
        def add_polygon(self, poligono, name: str):
            self.lista[name]=poligono
        def remove_polygon(self, name: str):
            self.lista.pop(name)
        def save_to_file(self, filename: str):
            with open(f'{filename}.txt','w') as file:
                  file.write(str(self.lista))#Tenho que mudar, preciso escrever em um formato legal
        def load_from_file(self, filename: str):
            with open(f'{filename}.txt','r') as file:
                self.lista =file.read()
        
            def __str__(self):
              return str(len(self.lista.keys()))#botei len só pq eu queria testar
		
			
p1 = Point2D(1, 2)
p2 = Point2D(3, 4)
p3 = Point2D(5, 6)
p4 = Point2D(7, 8)

triangle = Polygon([p1, p2, p3], 'red')
rectangle = Polygon([p1, p2, p3, p4], 'blue')
teste=polygons()
teste.add_polygon(triangle,'tri')
teste.add_polygon(rectangle,'re')
teste.save_to_file('teste')
"""print(teste)"""
teste_ler=polygons().load_from_file('teste')
"""print(teste_ler)"""

# prova

#Dias da semana
dias = ["Domingo", "Segunda", "Terça", "Quarta", "Quinta", "Sexta", "Sábado"]

#quantidade de lojas
n_lojas = int(input("lojas: "))

#vendas de todas as lojas (matriz)
lojas = []

#vendas
for i in range(n_lojas):
    print(f"\n======= Loja {i+1} =======")
    vendas = []  # lista interna da loja
    
    #7 vendas diárias
    for d in range(7):
        valor = float(input(f"Venda de {dias[d]}: R$ "))
        vendas.append(valor)
    
    #lista da loja à matriz
    lojas.append(vendas)

print("\n~~~~~~ RESULTADOS POR LOJA ~~~~~~\n")

totais_semanais = []  #totais de cada loja

#Processamento das lojas
for i in range(n_lojas):
    vendas = lojas[i]
    
    total = sum(vendas)
    media = total / 7
    maior = max(vendas)
    menor = min(vendas)
    
    dia_maior = dias[vendas.index(maior)]
    dia_menor = dias[vendas.index(menor)]
    
    totais_semanais.append(total)

    print(f"========= Loja {i+1} ========= ")
    print(f"  Total semanal: R$ {total:.2f}")
    print(f"  Média diária: R${media:.2f}")
    print(f"  Dia com Maior venda:({dia_maior}) R$ {maior:.2f} ")
    print(f"  Dia com Menor venda:({dia_menor})2 R$ {menor:.2f} ")

#lojas com maior e menor total
maior_total = max(totais_semanais)
menor_total = min(totais_semanais)

loja_maior = totais_semanais.index(maior_total) + 1
loja_menor = totais_semanais.index(menor_total) + 1

print("========== RESULTADO FINAL ==========")
print(f"Loja com MAIOR total semanal: Loja {loja_maior} (R$ {maior_total:.2f})")
print(f"Loja com MENOR total semanal: Loja {loja_menor} (R$ {menor_total:.2f})")

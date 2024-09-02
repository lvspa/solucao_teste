# solucao_teste
Solução para teste técnico da empresa Target Sistemas
-------------------------------------------------------------

#1

indice=13
soma=0
k=0
while k<indice:
    k+=1
    soma=soma+k
print(soma)



#2

def fibonacci(n):
    seq = [0, 1]
    while len(seq) < n:
        next_value = seq[-1] + seq[-2]
        seq.append(next_value)
    if n in seq:
        print("Esta dentro")
    return seq

n = int(input(""))
print(fibonacci(n))

#3

import json

def processar_faturamento(json_file):
    with open(json_file, 'r') as f:
        dados = json.load(f)

    faturamento = [dia['valor'] for dia in dados['faturamento_diario'] if dia['valor'] > 0]

    if not faturamento:
        return "Não há dados de faturamento para processar."

    menor_faturamento = min(faturamento)

    maior_faturamento = max(faturamento)

    media_mensal = sum(faturamento) / len(faturamento)

    dias_acima_da_media = sum(1 for valor in faturamento if valor > media_mensal)

    return {
        "menor_faturamento": menor_faturamento,
        "maior_faturamento": maior_faturamento,
        "dias_acima_da_media": dias_acima_da_media
    }

resultado = processar_faturamento('faturamento.json')

print(f"Menor valor de faturamento: R${resultado['menor_faturamento']:.2f}")
print(f"Maior valor de faturamento: R${resultado['maior_faturamento']:.2f}")
print(f"Dias com faturamento acima da média: {resultado['dias_acima_da_media']}")





#4

sp=67836.43
rj= 36678.66
mg=29229.88
es=27165.48
otr=19849.53
total=sp+rj+mg+es+otr
fatur_sp= (sp/total)*100
fatur_rj= (rj/total)*100
fatur_mg= (mg/total)*100
fatur_es= (es/total)*100
fatur_otr=(otr/total)*100
print(f"O Faturamento do estado São Paulo foi de:{fatur_sp:.1f}%")
print(f"O Faturamento do estado Rio de Janeiro foi de:{fatur_rj:.1f}%")
print(f"O Faturamento do estado Minas Gerais foi de:{fatur_mg:.1f}%")
print(f"O Faturamento do estado Espirito Santo foi de:{fatur_es:.1f}%")
print(f"O Faturamento de outros estados foram de:{fatur_otr:.1f}%")





#5

palavra=input("Insira a palavra: ")
fat_list=list(palavra)
for i in range(len(fat_list)-1):
    for j in range(len(fat_list)-1-i):
        fat_list[j], fat_list[j+1] = fat_list[j+1], fat_list[j]
print(fat_list)

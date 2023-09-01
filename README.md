# coded

#programa em loop
def calcular_conta_loop():
    n = int(input("Digite o número de itens: "))
    matriz_itens = []

    for i in range(n):
        preco = float(input(f"Digite o preço do item {i + 1}: "))
        quantidade = int(input(f"Digite a quantidade do item {i + 1}: "))
        subtotal = preco * quantidade
        matriz_itens.append([preco, quantidade, subtotal])

    total_conta = sum(item[2] for item in matriz_itens)
    print(f"Valor total da conta: R${total_conta:.2f}")

calcular_conta_loop()




#programa recursiva
def calcular_conta_recursiva(items, index=0):
    if index >= len(items):
        return 0
    
    quantidade, preco = items[index]
    subtotal = quantidade * preco
    return subtotal + calcular_conta_recursiva(items, index + 1)

# Recebe o número de itens do pedido do cliente
n = int(input("Digite o número de itens: "))

matriz_itens = []
for _ in range(n):
    quantidade = int(input("Digite a quantidade do item: "))
    preco = float(input("Digite o preço do item: "))
    matriz_itens.append([quantidade, preco])

total_conta = calcular_conta_recursiva(matriz_itens)
print(f"Valor total da conta: R${total_conta:.2f}")

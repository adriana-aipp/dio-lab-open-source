
menu = """
     ===============  Menu Principal  ================ 

     Seja bem vindo ao nosso ambiente digital!

     Por favor digite a opção desejada:

     1 - Depositar
     2 - Sacar
     3 - Extrato
     0 - Sair

     ================================================= 
     """


saldo= 0.00 # (valor do saldo inicializado para poder testar o programa)
extrato_conta = " " #(Varíavel para acumular transações de saque e depósito)
qtde_saque = 0 #(usado como contador para controlar qtde de transações de saque
limite_diario = 1500.00 #(valor máximo de saque ao dia)
limite_por_saque = 500.00 #(valor máximo por transação de saque ao dia)
LIMITE_DE_SAQUE = 3 #(qtde máxima de transação de saque ao dia)
#opcao = 0 #(controle de acesso ao menu)

#saque vai ser um input do usuário

while True:
    
    opcao = (int(input("\n""Selecione a opção desejada: ")))

    if opcao == 1:

      
      print("Saldo disponível",saldo)
      valor_deposito = (float(input("Informe o valor do depósito: ")))
      if valor_deposito <= 0:
        print ("Digite um valor maior que 0:")
      
      elif valor_deposito > 0:
        saldo += valor_deposito
        extrato_conta+=f"\nDepósito: R$ {valor_deposito:.2f}\n"
        print("-----Resumo da Conta-----\n""Saldo: ",saldo)
        print("Valor do Depósito: ", valor_deposito,"\n")
       # print(extrato_conta)
        
        
    elif opcao == 2:
                       
      valor_saque =float(input("Informe o valor do saque: "))

      if saldo >= valor_saque:
       
        if valor_saque <= limite_por_saque and qtde_saque <= LIMITE_DE_SAQUE and valor_saque > 0:
              
              print("Saque autorizado!")
              print("Saldo Disponível antes do Saque:", saldo)
              saldo-=valor_saque
              print("Saldo atualizado após o saque: ", saldo)
                 
              extrato_conta +=f"\nSaque realizado R$ {valor_saque:.2f}\n"
              #print("lista extrato""\n",  extrato_conta)
              

        elif qtde_saque >= LIMITE_DE_SAQUE:
          print("Limite de Saque diário excedido")
          break

        elif valor_saque <= 0:
          print("Valor inválido, digite um valor positivo > 0")
          

        else: print("Valor informado maior que o permitido por operação, informe valor até R$ 500,00")
                     
      else:
         print ("Saldo insuficiente")
         
               
    elif opcao == 3:
      
      print("\n""-------Resumo da Conta: Extrato------")
      print("\n"f"Saldo Disponível:----------R$ {saldo:.2f}","\n")
      if extrato_conta == " " :
         print("Sem movimentação atual""\n")
      else: 
         print (extrato_conta)

      
    elif opcao == 0:
      print("* Obrigado por utilizar os nossos serviços *")
      break
    
    else:
      print("Opção inválida, favor digitar novamente as opções disponíveis")
      opcao = (input("Selecione a opção desejada: "))



#print("A opção desejada foi",opcao)
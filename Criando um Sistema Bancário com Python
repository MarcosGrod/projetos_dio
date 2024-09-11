# Definindo as variáveis e constantes
ligado=True # Para controlar o loop
saldo=float(500.00) # Saldo da conta
LIMITE_DE_SAQUES=3 # Limite de 3 saques que podem ser feitos
saques_realizados=0 # Quantidade de saques já realizados
VALOR_LIMITE_DE_SAQUE=float(500) # Valor limite por saque
extrato="" # A string que conterá todas as movimentações da conta

# Lista as opções de telas possíveis, a ser usada na exibição das opções escolhidas pelo usuário
TELAS_POSSIVEIS = ['MENU_SAIDA', 'MENU_SUPORTE', 'MENU_INICIAR','MENU_CONTA','MENU_SAQUE',"MENU_DEPOSITO",'MENU_DEPOSITO_REALIZADO','MENU_EXTRATO']

# Função para verificar se a tela escolhida no comando condiz com os valores de TELAS_POSSIVEIS.
# Para a mudança de telas decorrente da ação do usuário, use tela=escolher_tela('NOME_DA_TELA') para evitar erros de digitação que causem falha no código
def escolher_tela(value):
    if value in TELAS_POSSIVEIS:
        return value
    else:
        raise ValueError(f"Valor inválido: {value}. Deve ser uma das telas: {TELAS_POSSIVEIS}.")
    
# Constante de bloco de texto a ser utilizado. Referência para as cores utilizadas a partir daqui: https://en.wikipedia.org/wiki/ANSI_escape_code#Colors
ACAO_INVALIDA="\x1b[0;30;41mAção inválida. Envie apenas o número da opção desejada.\x1b[0m"

tela=escolher_tela('MENU_INICIAR') # Iniciar o programa a partir da tela MENU_INICIAR
while ligado==True: # Loop para manter a sequência ligada

# Funcionamento do código: se iniciar com loop para manter o código rodando. Cada "elif tela=='MENU_...'" se resume ao print da tela para o usuário,
# recebimento e verificação da resposta dentro de um bloco try/except, caso a resposta seja válida, sequência de "ifs" para efetuar alguma ação. 

    if tela=='MENU_INICIAR': # Menu inicial, com opções de entrar na conta ou acessar o suporte (meu contato)
        print("""
 \x1b[0;30;43m╔════════════════════════════════╗\x1b[0m
 \x1b[0;30;43m║\x1b[0m          \x1b[1;33;40mBanco Python\x1b[0m          \x1b[0;30;43m║\x1b[0m
 \x1b[0;30;43m╚════════════════════════════════╝\x1b[0m

 \x1b[0;32;40mDigite o número da opção desejada\x1b[0m
 1. Entrar na sua conta
 2. Suporte

 \x1b[0;30;43m══════════════════════════════════\x1b[0m""")
        while True: # Bloco para receber e verificar a escolha do usuário
            try:
                escolha=int(input("Opção:")) #Receber escolha
                if escolha==1 or escolha==2: #Verificar se o input condiz com as opções válidas
                    break
                else:
                    print("\x1b[0;30;41mValor inválido! Opções disponíveis: '1'\x1b[0m")
            except ValueError:
                print(ACAO_INVALIDA)
        if escolha==1:
            tela=escolher_tela('MENU_CONTA')
        elif escolha==2:
            tela=escolher_tela('MENU_SUPORTE')
        else:
            print(ACAO_INVALIDA)
    elif tela=='MENU_SUPORTE': # Menu com meu contato
        print("""
 \x1b[0;30;43m╔════════════════════════════════╗\x1b[0m
 \x1b[0;30;43m║\x1b[0m          \x1b[1;33;40mBanco Python\x1b[0m          \x1b[0;30;43m║\x1b[0m
 \x1b[0;30;43m╚════════════════════════════════╝\x1b[0m

 \x1b[0;32;40mE-mail: marcosgrod@gmail.com\x1b[0m

 1. Retornar
 \x1b[0;30;43m══════════════════════════════════\x1b[0m""")
        while True:
            try:
                escolha=int(input("Opção:"))
                if escolha==1:
                    break
                else:
                    print("\x1b[0;30;41mValor inválido! Opções disponíveis: '1'\x1b[0m")
            except ValueError:
                print(ACAO_INVALIDA)
        if escolha==1:
            tela=escolher_tela('MENU_INICIAR')
    elif tela=='MENU_CONTA': # Menu a partir do qual o cliente selecionará qual ação realizar (saque, depósito, extrato) ou caso queira encerrar o programa
        print("""
 \x1b[0;30;43m╔════════════════════════════════╗\x1b[0m
 \x1b[0;30;43m║\x1b[0m          \x1b[1;33;40mBanco Python\x1b[0m          \x1b[0;30;43m║\x1b[0m
 \x1b[0;30;43m╚════════════════════════════════╝\x1b[0m

 \x1b[0;32;40mDigite o número da opção desejada\x1b[0m
 1. Sacar
 2. Depositar
 3. Extrato
 4. Tela inicial
 5. Sair da conta

 \x1b[0;30;43m══════════════════════════════════\x1b[0m""")
        while True:
            try:
                escolha=int(input("Opção:")) #Receber escolha
                if escolha==1 or escolha==2 or escolha==3 or escolha==4 or escolha==5: #Verificar se o input condiz com as opções válidas
                    break
                else:
                    print("\x1b[0;30;41mValor inválido! Opções disponíveis: '1'\x1b[0m")
            except ValueError:
                print(ACAO_INVALIDA)
        if escolha==1:
            tela=escolher_tela('MENU_SAQUE')
        elif escolha==2:
            tela=escolher_tela('MENU_DEPOSITO')
        elif escolha==3:
            tela=escolher_tela('MENU_EXTRATO')
        elif escolha==4:
            tela=escolher_tela('MENU_INICIAR')
        elif escolha==5: # Esta escolha define a variável "ligado" como False, encerrando o loop e "desligando" o banco
            print("""
 \x1b[0;30;43m╔════════════════════════════════╗\x1b[0m
 \x1b[0;30;43m║\x1b[0m          \x1b[1;33;40mBanco Python\x1b[0m          \x1b[0;30;43m║\x1b[0m
 \x1b[0;30;43m╚════════════════════════════════╝\x1b[0m

 \x1b[0;32;40mVocê saiu da sua conta com sucesso.
 Tenha um ótimo dia!\x1b[0m

 \x1b[0;30;43m══════════════════════════════════\x1b[0m""")
            ligado=False
        else:
            print(ACAO_INVALIDA)
    elif tela=='MENU_SAQUE': # Menu de saque. É o primeiro com código significativamente diferente das anteriores
        print(f"""
 \x1b[0;30;43m╔════════════════════════════════╗\x1b[0m
 \x1b[0;30;43m║\x1b[0m          \x1b[1;33;40mBanco Python\x1b[0m          \x1b[0;30;43m║\x1b[0m
 \x1b[0;30;43m╚════════════════════════════════╝\x1b[0m

 \x1b[0;32;40mSeu saldo é de:\x1b[0m R${saldo:.2f}
 \x1b[0;32;40mQuanto deseja sacar?\x1b[0m
 
 \x1b[0;32;40mSaques realizados hoje:\x1b[0m {saques_realizados}/{LIMITE_DE_SAQUES}

 Digite "0" para cancelar a operação e retornar ao menu.
 \x1b[0;30;43m══════════════════════════════════\x1b[0m""") # Mostra o saldo atual, a quantidade de saques realizados e o limite de 3 saques estabelecidos nos comandos do projeto DIO
        while tela=='MENU_SAQUE':
            while True:
                try:
                    valor_saque = float(input("Valor:")) # Verifica se o valor pode ser convertido para float, causando erro caso seja letra, símbolo ou não haja entrada. Mais verificações são feitas pelos "ifs"
                    break
                except ValueError:
                    print(ACAO_INVALIDA)
            if valor_saque==float(0.0): # Caso a entrada seja 0, cancela a operação de saque e retorna ao menu da conta, não contando a operação como saque realizado
                tela=escolher_tela('MENU_CONTA')
            elif valor_saque<0: # Impede que o valor seja inferior a 0 (ninguém quer sacar uma dívida)
                print(f"\x1b[0;30;41mO valor escolhido deve ser número racional positivo. Digite um novo valor \x1b[0m")
            elif valor_saque>VALOR_LIMITE_DE_SAQUE: # Verifica se o valor está dentro do limite de 500 estabelecido nos comandos do projeto DIO
                print(f"\x1b[0;30;41mO valor escolhido de {valor_saque} excede o limite de {VALOR_LIMITE_DE_SAQUE}. Digite um novo valor \x1b[0m")
            elif saques_realizados>=LIMITE_DE_SAQUES: # Verifica se o usuário já atingiu o limite de 3 saques
                print(f"\x1b[0;30;41mVocê já atingiu o limite de {LIMITE_DE_SAQUES} saques diários. \x1b[0m")
            elif valor_saque>saldo: # Verifica se o cliente possui saque suficiente para realizar o saldo
                print(f"\x1b[0;30;41mO valor solicitado de {valor_saque} excede o saldo de {saldo}. \x1b[0m")
            else: # Caso não haja nenhum erro na entrada, segue com a operação
                saldo=saldo-valor_saque # Define o novo saldo, subtraindo deste o valor sacado pelo cliente
                saques_realizados+=1 # Contabiliza a operação realizada por conta do limite de 3 saques
                extrato+=f"\n Saque de \x1b[0;31;40m{valor_saque}\x1b[0m" # Adiciona a operação realizada ao extrato.
                print(f"""
 \x1b[0;30;43m╔════════════════════════════════╗\x1b[0m
 \x1b[0;30;43m║\x1b[0m          \x1b[1;33;40mBanco Python\x1b[0m          \x1b[0;30;43m║\x1b[0m
 \x1b[0;30;43m╚════════════════════════════════╝\x1b[0m

 \x1b[0;32;40mRealizou saque de:\x1b[0m R${valor_saque:.2f}
 \x1b[0;32;40mSaldo atual:\x1b[0m R${saldo}
 
 Digite qualquer coisa para retornar ao menu
 \x1b[0;30;43m══════════════════════════════════\x1b[0m""")
                escolha=input('Opção:') # Independentemente do input, retorna o cliente para o menu da conta
                if escolha==0:
                    tela=escolher_tela('MENU_CONTA')
                else:
                    tela=escolher_tela('MENU_CONTA')
    elif tela=='MENU_DEPOSITO': # Menu de depósito, código semelhante ao menu de saque, mas com menos verificações do input (por não haver limite máximo de depósito nem quantidade de depósitos)
        print(f"""
 \x1b[0;30;43m╔════════════════════════════════╗\x1b[0m
 \x1b[0;30;43m║\x1b[0m          \x1b[1;33;40mBanco Python\x1b[0m          \x1b[0;30;43m║\x1b[0m
 \x1b[0;30;43m╚════════════════════════════════╝\x1b[0m

 \x1b[0;32;40mSeu saldo é de:\x1b[0m R${saldo:.2f}
 \x1b[0;32;40mQuanto deseja depositar?\x1b[0m
 
 Para cancelar, digite 0
 \x1b[0;30;43m══════════════════════════════════\x1b[0m""")
        while tela=='MENU_DEPOSITO':
            while True:
                try:
                    valor_deposito = float(input("Valor:")) # Verifica se o valor pode ser convertido para float, causando erro caso seja letra, símbolo ou não haja entrada. Mais verificações são feitas pelos "ifs"
                    break
                except ValueError:
                    print(ACAO_INVALIDA)
            if valor_deposito==float(0.0): # Caso a entrada seja 0, cancela a operação de saque e retorna ao menu da conta, não contando a operação como saque realizado
                tela=escolher_tela('MENU_CONTA')
            elif valor_deposito<0: # Impede que o valor seja inferior a 0
                print(f"\x1b[0;30;41mO valor escolhido deve ser número racional positivo. Digite um novo valor \x1b[0m")
            else: # Caso não haja nenhum erro na entrada, segue com a operação
                saldo=saldo+valor_deposito # Redefine o saldo somando a este o valor depositado
                extrato = extrato+f"\n Depósito de \x1b[0;32;40m{valor_deposito}\x1b[0m" # Acrescenta a operação ao extrato da conta
                print(f"""
 \x1b[0;30;43m╔════════════════════════════════╗\x1b[0m
 \x1b[0;30;43m║\x1b[0m          \x1b[1;33;40mBanco Python\x1b[0m          \x1b[0;30;43m║\x1b[0m
 \x1b[0;30;43m╚════════════════════════════════╝\x1b[0m

 \x1b[0;32;40mRealizou depósito de:\x1b[0m R${valor_deposito}
 \x1b[0;32;40mSaldo atual:\x1b[0m R${saldo}
 
 Digite qualquer coisa para retornar ao menu
 \x1b[0;30;43m══════════════════════════════════\x1b[0m""")
                escolha=input('Opção:') # Retorna ao menu da conta independentemente do input recebido
                if escolha==0:
                    tela=escolher_tela('MENU_CONTA')
                else:
                    tela=escolher_tela('MENU_CONTA')
    elif tela=='MENU_EXTRATO': # Extrato de movimentações da conta. Valores de saque em vermelho e valores de depósito em verde para facilitar o entendimento do cliente.
        print(f"""
 \x1b[0;30;43m╔════════════════════════════════╗\x1b[0m
 \x1b[0;30;43m║\x1b[0m          \x1b[1;33;40mBanco Python\x1b[0m          \x1b[0;30;43m║\x1b[0m
 \x1b[0;30;43m╚════════════════════════════════╝\x1b[0m

 \x1b[0;32;40mExtrato da conta:\x1b[0m
 {extrato}

 \x1b[0;32;40mSaldo:\x1b[0m R${saldo:.2f}
 
 Digite 0 para retornar ao menu anterior
 \x1b[0;30;43m══════════════════════════════════\x1b[0m""")
        while True:
            try:
                escolha=int(input("Opção:"))
                if escolha==0:
                    break
                else:
                    print("\x1b[0;30;41mValor inválido! Opções disponíveis: '0'\x1b[0m")
            except ValueError:
                print(ACAO_INVALIDA)
        if escolha==0:
            tela=escolher_tela('MENU_CONTA')
        else:
            print(ACAO_INVALIDA)
    else: # caso haja algum bug que fuja aos testes realizados até o momento.
        print('Uepa, aconteceu algum problema. Entre em contato comigo pra notificar')

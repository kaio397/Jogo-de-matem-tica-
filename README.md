import random

def apresentar_enigma(enigma, resposta):
    """Apresenta o enigma e verifica a resposta do jogador."""
    print("\nEnigma:")
    print(enigma)
    while True:
        try:
            resposta_jogador = float(input("Sua resposta: "))
            if resposta_jogador == resposta:
                print("Resposta correta!")
                return True
            else:
                print("Resposta incorreta. Tente novamente.")
        except ValueError:
            print("Por favor, digite um número.")

def jogar():
    """Função principal do jogo."""
    print("Bem-vindo à Busca do Tesouro Matemático na Bahia Colonial!")
    print("Decifre os enigmas para encontrar o tesouro escondido.")

    enigmas = [
        {"pergunta": "Um comerciante trouxe de Salvador 3 arrobas de açúcar. Se cada arroba pesa aproximadamente 15 kg, quantos quilos de açúcar ele possui no total?", "resposta": 45, "pista": "A próxima pista está perto da 'Igreja Matriz'."},
        {"pergunta": "Para construir uma casa, foram utilizados 500 tijolos. Se cada tijolo custou 8 vinténs, qual o custo total em réis (considerando que 20 vinténs equivalem a 1 real)?", "resposta": 200, "pista": "Procure perto do 'Mercado Municipal'."},
        {"pergunta": "Um terreno retangular mede 20 braças de comprimento por 15 braças de largura. Qual a área total em braças quadradas?", "resposta": 300, "pista": "O tesouro pode estar nos arredores da 'Fazenda Velha'."},
        {"pergunta": "Uma caravana leva 2 semanas e 3 dias para chegar de Feira de Santana até o litoral. Quantos dias durou a viagem?", "resposta": 17, "pista": "A próxima pista se encontra onde os escravos buscavam água: a 'Fonte da Bica'."},
        {"pergunta": "Na plantação de café, 4 trabalhadores colheram juntos 12 sacas em um dia. Se eles mantiverem o mesmo ritmo, quantas sacas colherão em 5 dias?", "resposta": 60, "pista": "Siga em direção ao antigo 'Casarão dos Barões'."},
        {"pergunta": "Um artesão vendeu 5 colares de prata por 320 réis cada e 3 pulseiras de ouro por 510 réis cada. Qual o valor total da venda em réis?", "resposta": 3130, "pista": "A penúltima pista está gravada no sino da 'Capela de Santana'."},
        {"pergunta": "No alto da Capela de Santana, você observa o Largo da Matriz. Se o número de degraus para subir a torre sineira é igual ao número de dezenas de anos desde que Feira de Santana foi elevada à categoria de cidade (em 1833) multiplicado por 2, quantos degraus você precisa subir?", "resposta": 38, "pista": "O tesouro final aguarda sob a sombra da grande mangueira no centro do 'Largo da Matriz'."}
    ]

    localizacao_atual = "Início da Jornada"

    for i, enigma_atual in enumerate(enigmas):
        print(f"\nVocê está em: {localizacao_atual}")
        if apresentar_enigma(enigma_atual["pergunta"], enigma_atual["resposta"]):
            print(f"Pista encontrada: {enigma_atual['pista']}")
            localizacao_atual = f"Seguindo a pista para: {enigma_atual['pista'].split()[-1].strip('\'')}" # Simplificação para a próxima "localização"
        else:
            print("A busca termina aqui...")
            return

    print("\nParabéns! Você decifrou o mapa e encontrou o tesouro sob a grande mangueira no Largo da Matriz!")

if __name__ == "__main__":
    jogar()

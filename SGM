# SGM - SISTEMA DE GESTÃO DE MINIATURAS

class Miniatura:
    def __init__(self, id_item, heroi, universo, fabricante, preco_compra, estado):
        self.id = id_item
        self.heroi = heroi
        self.universo = universo  # Marvel, DC, Vertigo, etc.
        self.fabricante = fabricante  # Iron Studios, Panini, Funko, Hot Toys
        self.preco_compra = preco_compra
        self.estado = estado  # Nova na Caixa, Exposta, Com Detalhes

    def exibir_detalhes(self):
        return f"ID: {self.id} | {self.heroi} ({self.universo}) - {self.fabricante} [{self.estado}] | Pago: R$ {self.preco_compra:.2f}"


class GerenciadorColecao:
    def __init__(self):
        self.colecao = []
        # Dados iniciais
        self.colecao.append(Miniatura(1, "Batman (Cavaleiro das Trevas)", "DC", "Iron Studios", 450.00, "Exposto"))
        self.colecao.append(Miniatura(2, "Homem de Ferro (Mark 85)", "Marvel", "Hot Toys", 2100.00, "Nova na Caixa"))
        self.colecao.append(Miniatura(3, "Batman (Frank Miller)", "DC", "Panini", 100.00, "Exposto"))

    def adicionar_item(self):
        print("\n--- NOVO CADASTRO ---")
        id_item = len(self.colecao) + 1
        heroi = input("Nome do Super-Herói / Versão: ")
        universo = input("Universo (Marvel/DC/Vertigo/Outro): ")
        fabricante = input("Fabricante/Marca: ")
        preco = float(input("Preço de Compra (R$): "))
        estado = input("Estado de Conservação (Nova na caixa / Exposto): ")
        
        novo_item = Miniatura(id_item, heroi, universo, fabricante, preco, estado)
        self.colecao.append(novo_item)
        print("✅ Miniatura catalogada com sucesso!")

    def listar_colecao(self):
        print("\n--- SEU ACERVO DE MINIATURAS ---")
        if not self.colecao:
            print("Nenhum item cadastrado.")
            return
        
        for item in self.colecao:
            print(item.exibir_detalhes())

    def exibir_dashboard(self):
        print("\n==========================================")
        print("         ESTATÍSTICAS DA COLEÇÃO          ")
        print("==========================================")
        total_itens = len(self.colecao)
        total_investido = sum(item.preco_compra for item in self.colecao)
        
        # Contagem rápida por Universo
        marvel_count = sum(1 for item in self.colecao if item.universo.lower() == "marvel")
        dc_count = sum(1 for item in self.colecao if item.universo.lower() == "dc")
        
        print(f"Total de Miniaturas: {total_itens}")
        print(f"Valor Total do Patrimônio: R$ {total_investido:.2f}")
        print(f"Itens da Marvel: {marvel_count} | Itens da DC: {dc_count}")
        print("==========================================")


# --- FLUXO PRINCIPAL DO SISTEMA ---
if __name__ == "__main__":
    gerenciador = GerenciadorColecao()
    
    while True:
        print("\n=== SISTEMA DE GESTÃO: SGM HERO COLLECT ===")
        print("1. Catalogar Nova Miniatura")
        print("2. Ver Minhas Miniaturas")
        print("3. Ver Dashboard / Valor Total")
        print("4. Sair")
        
        opcao = input("Escolha uma opção: ")
        
        if opcao == "1":
            try:
                gerenciador.add_item = gerenciador.adicionar_item()
            except ValueError:
                print("⚠️ Erro nos dados informados. Tente novamente.")
        elif opcao == "2":
            gerenciador.listar_colecao()
        elif opcao == "3":
            gerenciador.exibir_dashboard()
        elif opcao == "4":
            print("Encerrando o SGM Hero Collect. Até a próxima!")
            break
        else:
            print("Opção inválida.")
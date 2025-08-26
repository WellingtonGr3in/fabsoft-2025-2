# Fábrica de Software 2025

Curso de Engenharia de Software 

Nome da equipe: Wellington Grein
# Propostas de projeto

* Site de Venda de Lanches

* RF01 - Cadastro de Usuário
* RF02 - Login e Autenticação
* RF03 - Cadastro de Produtos
* RF04 - Edição de Produtos
* RF05 - Listagem de Produtos
* RF06 - Filtro de Produtos por Categoria
* RF07 - Adicionar Item ao Carrinho
* RF08 - Remover Item do Carrinho	
* RF09 - Visualizar Carrinho
* RF10 - Finalizar Pedido
* RF11 - Favoritar Produtos
* RF12 - Visualizar Produtos Favoritos
* RF13 - Histórico de Pedidos
* RF14 - Geração de Relatório de Vendas
* RF15 - Gestão de Estoque
* RF16 - Administração de Usuários

      
## Histórias de usuário
   * Eu como cliente, gostaria de me cadastrar no site
   * Eu como cliente, gostaria de fazer login no site
   * Eu como cliente, gostaria de visualizar todos os produtos
   * Eu como cliente, gostaria de filtrar produtos por categoria
   * Eu como cliente, gostaria de adicionar um item ao carrinho
   * Eu como cliente, gostaria de remover itens do carrinho
   * Eu como cliente, gostaria de favoritar um item
   * Eu como cliente, gostaria de ver meus produtos favoritos
   * Eu como cliente, gostaria de finalizar um pedido
   * Eu como cliente, gostaria de ver meu histórico de pedidos
   * Eu como funcionário, gostaria de realizar o cadastro de itens*
   * Eu como funcionário, gostaria de editar produtos existentes
   * Eu como funcionário, gostaria de gerenciar o estoque
   * Eu como funcionário, gostaria de visualizar relatório de vendas
   * Eu como funcionário, gostaria de gerenciar usuários do sistema

     
```mermaid
---
title: Diagrama de Classes - Sistema Lanchonete
---
classDiagram
    Usuario "1" --> "*" Pedido
    Usuario "1" --> "*" Favorito
    Usuario "1" --> "*" Carrinho
    Pedido "1" --> "*" ItemPedido
    ItemPedido "*" --> "1" Produto
    Favorito "*" --> "1" Produto
    Carrinho "*" --> "1" Produto
    
    namespace entity {
        class Usuario {
            -id : Long
            -nome : String
            -email : String
            -senha : String
            -endereco : String
            -telefone : String
            -dataNascimento: Date

            +getId() Long
            +setId(id:Long) void
            +getNome() String
            +setNome(nome:String) void
            +getEmail() String
            +setEmail(email:String) void
            +getSenha() String
            +setSenha(senha:String) void
            +getEndereco() String
            +setEndereco(endereco:String) void
            +getTelefone() String
            +setTelefone(telefone:String) void
            +getDataNascimento() Date
            +setDataNascimento(dataNascimento:Date) void
        }

        class Produto {
            -id : Long
            -nome : String
            -descricao : String
            -preco : Decimal
            -imagemUrl : String
            -categoria : String
            -emEstoque : Boolean

            +getId() Long
            +setId(id:Long) void
            +getNome() String
            +setNome(nome:String) void
            +getDescricao() String
            +setDescricao(descricao:String) void
            +getPreco() Decimal
            +setPreco(preco:Decimal) void
            +getImagemUrl() String
            +setImagemUrl(imagemUrl:String) void
            +getCategoria() String
            +setCategoria(categoria:String) void
            +isEmEstoque() Boolean
            +setEmEstoque(emEstoque:Boolean) void
        }

        class Pedido {
            -id : Long
            -usuarioId : Long
            -dataPedido : Date
            -status : String
            -total : Decimal
            -enderecoEntrega : String

            +getId() Long
            +setId(id:Long) void
            +getUsuarioId() Long
            +setUsuarioId(usuarioId:Long) void
            +getDataPedido() Date
            +setDataPedido(dataPedido:Date) void
            +getStatus() String
            +setStatus(status:String) void
            +getTotal() Decimal
            +setTotal(total:Decimal) void
            +getEnderecoEntrega() String
            +setEnderecoEntrega(enderecoEntrega:String) void
        }

        class ItemPedido {
            -id : Long
            -pedidoId : Long
            -produtoId : Long
            -quantidade : Int
            -precoUnitario : Decimal

            +getId() Long
            +setId(id:Long) void
            +getPedidoId() Long
            +setPedidoId(pedidoId:Long) void
            +getProdutoId() Long
            +setProdutoId(produtoId:Long) void
            +getQuantidade() Int
            +setQuantidade(quantidade:Int) void
            +getPrecoUnitario() Decimal
            +setPrecoUnitario(precoUnitario:Decimal) void
        }

        class Carrinho {
            -id : Long
            -usuarioId : Long
            -produtoId : Long
            -quantidade : Int

            +getId() Long
            +setId(id:Long) void
            +getUsuarioId() Long
            +setUsuarioId(usuarioId:Long) void
            +getProdutoId() Long
            +setProdutoId(produtoId:Long) void
            +getQuantidade() Int
            +setQuantidade(quantidade:Int) void
        }

        class Favorito {
            -id : Long
            -usuarioId : Long
            -produtoId : Long

            +getId() Long
            +setId(id:Long) void
            +getUsuarioId() Long
            +setUsuarioId(usuarioId:Long) void
            +getProdutoId() Long
            +setProdutoId(produtoId:Long) void
        }

        class Relatorio {
            -id : Long
            -dataGeracao : Date
            -tipo : String
            -dados : String

            +getId() Long
            +setId(id:Long) void
            +getDataGeracao() Date
            +setDataGeracao(dataGeracao:Date) void
            +getTipo() String
            +setTipo(tipo:String) void
            +getDados() String
            +setDados(dados:String) void
        }
    }
```

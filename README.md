# Exercicio de Composicao-JAVA-
Exercicio de composicação em JAVA. Abaixo, segue o diagrama de classe o qual o exercício foi baseado.

##Enunciado
Ler os dados de um pedido com N itens (N fornecido pelo usuário). Depois, mostrar um 
sumário do pedido conforme exemplo (próxima página). Nota: o instante do pedido deve ser 
o instante do sistema: new Date()

```mermaid
classDiagram
    Order --> OrderItem : items
    Order --> Client : client
    OrderItem --> Product : product
    OrderStatus : <<enum>>
    OrderStatus : PENDING_PAYMENT = 0
    OrderStatus : PROCESSING = 1
    OrderStatus : SHIPPED = 2
    OrderStatus : DELIVERED = 3

    class Order {
        - moment : Date
        - status : OrderStatus
        + addItem(item : OrderItem) : void
        + removeItem(item : OrderItem) : void
        + total() : Double
    }

    class Client {
        - name : String
        - email : String
        - birthDate : Date
    }

    class OrderItem {
        - quantity : Integer
        - price : Double
        + subTotal() : Double
    }

    class Product {
        - name : String
        - price : Double
    }
   
```
